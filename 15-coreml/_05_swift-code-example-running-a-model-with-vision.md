# Core ML — Swift code example: running a model with Vision

```swift
import Vision
import CoreML
import UIKit

func classify(image: UIImage) {
    guard let cgImage = image.cgImage else { return }

    // Load the Core ML model with a compute-unit hint
    let config = MLModelConfiguration()
    config.computeUnits = .all  // let Core ML choose CPU/GPU/ANE per layer

    guard let coreMLModel = try? MyImageClassifier(configuration: config),
          let visionModel = try? VNCoreMLModel(for: coreMLModel.model) else {
        return
    }

    let request = VNCoreMLRequest(model: visionModel) { request, error in
        guard let results = request.results as? [VNClassificationObservation],
              let top = results.first else { return }
        print("Prediction: \(top.identifier) confidence: \(top.confidence)")
    }
    request.imageCropAndScaleOption = .centerCrop

    let handler = VNImageRequestHandler(cgImage: cgImage, options: [:])
    do {
        try handler.perform([request])
    } catch {
        print("Vision request failed: \(error)")
    }
}
```

`VNCoreMLRequest` handles image resizing/cropping/pixel-format conversion to match the model's expected input automatically, which is why routing vision models through Vision rather than calling `MyImageClassifier.prediction(...)` directly is the common pattern for image tasks.
