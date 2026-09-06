# iOS Edge AI — Code example (Swift, loading a Core ML model)

```swift
import CoreML
import Vision

func loadModel() throws -> MLModel {
    let config = MLModelConfiguration()
    config.computeUnits = .all // let Core ML choose CPU/GPU/ANE

    // Using the Xcode-generated wrapper class (from MyModel.mlpackage):
    let model = try MyModel(configuration: config).model
    return model
}

func runInference(model: MLModel, pixelBuffer: CVPixelBuffer) throws -> MLFeatureProvider {
    let input = try MLDictionaryFeatureProvider(dictionary: ["input": pixelBuffer])
    return try model.prediction(from: input)
}

// Or, for vision-shaped models, wrap with the Vision framework:
func makeVisionRequest(model: MLModel, completion: @escaping (VNRequest, Error?) -> Void) throws -> VNCoreMLRequest {
    let visionModel = try VNCoreMLModel(for: model)
    return VNCoreMLRequest(model: visionModel, completionHandler: completion)
}
```

Using the on-device foundation model (iOS 18+ Foundation Models framework) is comparably lightweight:

```swift
import FoundationModels

let session = LanguageModelSession()
let response = try await session.respond(to: "Summarize this note in one sentence: \(noteText)")
print(response.content)
```
