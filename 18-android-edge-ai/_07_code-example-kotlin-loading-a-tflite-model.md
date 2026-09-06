# Android Edge AI — Code example (Kotlin, loading a TFLite model)

```kotlin
import org.tensorflow.lite.Interpreter
import org.tensorflow.lite.gpu.CompatibilityList
import org.tensorflow.lite.gpu.GpuDelegate
import java.nio.MappedByteBuffer
import java.nio.channels.FileChannel
import android.content.res.AssetFileDescriptor
import android.content.Context

fun loadModelFile(context: Context, modelPath: String): MappedByteBuffer {
    val fd: AssetFileDescriptor = context.assets.openFd(modelPath)
    val inputStream = FileInputStream(fd.fileDescriptor)
    val channel = inputStream.channel
    return channel.map(FileChannel.MapMode.READ_ONLY, fd.startOffset, fd.declaredLength)
}

fun createInterpreter(context: Context): Interpreter {
    val options = Interpreter.Options()

    // Prefer GPU delegate when the device supports it, else fall back to CPU.
    val compatList = CompatibilityList()
    if (compatList.isDelegateSupportedOnThisDevice) {
        val delegateOptions = compatList.bestOptionsForThisDevice
        options.addDelegate(GpuDelegate(delegateOptions))
    } else {
        options.setNumThreads(4) // CPU fallback
    }

    val modelBuffer = loadModelFile(context, "model.tflite")
    return Interpreter(modelBuffer, options)
}

fun runInference(interpreter: Interpreter, input: Array<FloatArray>): Array<FloatArray> {
    val output = Array(1) { FloatArray(OUTPUT_SIZE) }
    interpreter.run(input, output)
    return output
}
```
