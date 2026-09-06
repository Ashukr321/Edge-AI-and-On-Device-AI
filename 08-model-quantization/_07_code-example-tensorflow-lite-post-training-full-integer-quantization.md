# Model Quantization — Code example — TensorFlow Lite post-training full-integer quantization

```python
import tensorflow as tf

def representative_dataset():
    for sample in calibration_samples:   # a small, representative dataset
        yield [sample.astype("float32")]

converter = tf.lite.TFLiteConverter.from_saved_model("saved_model_dir")
converter.optimizations = [tf.lite.Optimize.DEFAULT]
converter.representative_dataset = representative_dataset
converter.target_spec.supported_ops = [tf.lite.OpsSet.TFLITE_BUILTINS_INT8]
converter.inference_input_type = tf.int8
converter.inference_output_type = tf.int8

tflite_model = converter.convert()
with open("model_int8.tflite", "wb") as f:
    f.write(tflite_model)
```
