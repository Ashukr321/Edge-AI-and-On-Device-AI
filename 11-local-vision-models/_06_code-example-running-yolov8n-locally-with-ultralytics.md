# Local Vision Models — Code example: running YOLOv8n locally with Ultralytics

```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")  # nano model, ~6MB, downloads automatically
results = model("street.jpg")

for r in results:
    for box in r.boxes:
        cls = model.names[int(box.cls)]
        conf = float(box.conf)
        print(f"{cls}: {conf:.2f} at {box.xyxy.tolist()}")

results[0].save("street_annotated.jpg")
```

Equivalent inference via ONNX Runtime (after exporting `yolov8n.onnx`):

```python
import onnxruntime as ort
import numpy as np
from PIL import Image

session = ort.InferenceSession("yolov8n.onnx", providers=["CPUExecutionProvider"])
img = Image.open("street.jpg").resize((640, 640))
input_tensor = (np.asarray(img).astype(np.float32) / 255.0).transpose(2, 0, 1)[None]

outputs = session.run(None, {"images": input_tensor})
```
