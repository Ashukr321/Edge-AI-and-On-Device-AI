# TinyML — Code example — minimal TFLite Micro inference loop (C++)

```cpp
#include "tensorflow/lite/micro/all_ops_resolver.h"
#include "tensorflow/lite/micro/micro_interpreter.h"
#include "tensorflow/lite/micro/micro_log.h"
#include "tensorflow/lite/schema/schema_generated.h"
#include "model_data.h"  // generated C array: g_model[], g_model_len

// Statically allocated arena for tensors/activations — no malloc at runtime.
constexpr int kTensorArenaSize = 16 * 1024;
alignas(16) uint8_t tensor_arena[kTensorArenaSize];

const tflite::Model* model = nullptr;
tflite::MicroInterpreter* interpreter = nullptr;
TfLiteTensor* input = nullptr;
TfLiteTensor* output = nullptr;

void setup_model() {
  model = tflite::GetModel(g_model);
  if (model->version() != TFLITE_SCHEMA_VERSION) {
    MicroPrintf("Model schema mismatch!");
    return;
  }

  static tflite::AllOpsResolver resolver;  // or a MicroMutableOpResolver
                                            // with only the ops you need,
                                            // to save flash.
  static tflite::MicroInterpreter static_interpreter(
      model, resolver, tensor_arena, kTensorArenaSize);
  interpreter = &static_interpreter;

  interpreter->AllocateTensors();
  input = interpreter->input(0);
  output = interpreter->output(0);
}

void run_inference(const int8_t* sensor_frame, int len) {
  for (int i = 0; i < len; i++) {
    input->data.int8[i] = sensor_frame[i];  // already quantized int8
  }

  if (interpreter->Invoke() != kTfLiteOk) {
    MicroPrintf("Invoke failed");
    return;
  }

  int8_t best_score = -128;
  int best_class = -1;
  for (int i = 0; i < output->dims->data[1]; i++) {
    int8_t score = output->data.int8[i];
    if (score > best_score) { best_score = score; best_class = i; }
  }
  // best_class now holds the predicted label index
}
```
