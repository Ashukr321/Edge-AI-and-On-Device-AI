# Mobile AI — Code example

Minimal cross-platform-style inference using TensorFlow Lite's Python API (mirrors the on-device C++/Java/Swift API shape and is useful for prototyping before mobile integration):

```python
import numpy as np
import tensorflow as tf

interpreter = tf.lite.Interpreter(model_path="model.tflite")
interpreter.allocate_tensors()

input_details = interpreter.get_input_details()
output_details = interpreter.get_output_details()

input_shape = input_details[0]["shape"]
input_data = np.random.rand(*input_shape).astype(np.float32)

interpreter.set_tensor(input_details[0]["index"], input_data)
interpreter.invoke()

output_data = interpreter.get_tensor(output_details[0]["index"])
print(output_data)
```

On-device, the same `.tflite` file is loaded through the Java/Kotlin `Interpreter` class on Android or the Swift/Objective-C `TFLInterpreter` on iOS, with the delegate chosen per platform.
