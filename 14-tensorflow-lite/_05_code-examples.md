# TensorFlow Lite / LiteRT — Code examples

### Python: load and run a `.tflite` model

```python
import numpy as np
import tensorflow as tf

interpreter = tf.lite.Interpreter(
    model_path="model.tflite",
    num_threads=4,
)
interpreter.allocate_tensors()

input_details = interpreter.get_input_details()
output_details = interpreter.get_output_details()

input_data = np.random.rand(*input_details[0]["shape"]).astype(input_details[0]["dtype"])
interpreter.set_tensor(input_details[0]["index"], input_data)
interpreter.invoke()

output_data = interpreter.get_tensor(output_details[0]["index"])
print(output_data.shape)
```

### Kotlin (Android): load and run with the GPU delegate

```kotlin
import org.tensorflow.lite.Interpreter
import org.tensorflow.lite.gpu.GpuDelegate
import org.tensorflow.lite.gpu.CompatibilityList

val options = Interpreter.Options()
val compatList = CompatibilityList()

if (compatList.isDelegateSupportedOnThisDevice) {
    val delegateOptions = compatList.bestOptionsForThisDevice
    options.addDelegate(GpuDelegate(delegateOptions))
} else {
    options.setNumThreads(4) // fall back to XNNPACK CPU path
}

val interpreter = Interpreter(loadModelFile(context, "model.tflite"), options)

val input = Array(1) { FloatArray(224 * 224 * 3) }
val output = Array(1) { FloatArray(1000) }
interpreter.run(input, output)
```
