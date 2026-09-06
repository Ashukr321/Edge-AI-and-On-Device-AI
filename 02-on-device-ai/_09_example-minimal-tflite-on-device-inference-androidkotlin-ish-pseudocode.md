# On-Device AI — Example: minimal TFLite on-device inference (Android/Kotlin-ish pseudocode)

```kotlin
val options = Interpreter.Options().apply {
    setUseNNAPI(true)          // route to available NPU/DSP if present
    setNumThreads(4)
}
val interpreter = Interpreter(loadModelFile("model_int8.tflite"), options)

val input = preprocess(cameraFrame)     // resize + normalize to INT8
val output = Array(1) { FloatArray(NUM_CLASSES) }
interpreter.run(input, output)
val prediction = output[0].indices.maxBy { output[0][it] }
```
