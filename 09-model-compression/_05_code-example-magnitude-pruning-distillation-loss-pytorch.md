# Model Compression — Code example — magnitude pruning + distillation loss (PyTorch)

```python
import torch
import torch.nn as nn
import torch.nn.functional as F
import torch.nn.utils.prune as prune

# --- Structured/unstructured pruning ---
student = nn.Sequential(
    nn.Linear(768, 256), nn.ReLU(),
    nn.Linear(256, 10),
)

# Prune 40% of weights in the first Linear layer by L1 magnitude (unstructured).
prune.l1_unstructured(student[0], name="weight", amount=0.4)
# `student[0].weight` is now masked; call prune.remove(student[0], "weight")
# once fine-tuning is done to bake the mask into the dense tensor permanently.

# --- Knowledge distillation loss ---
def distillation_loss(student_logits, teacher_logits, labels, temperature=4.0, alpha=0.5):
    # Soft-label loss: match softened teacher distribution (KL divergence).
    soft_loss = F.kl_div(
        F.log_softmax(student_logits / temperature, dim=-1),
        F.softmax(teacher_logits / temperature, dim=-1),
        reduction="batchmean",
    ) * (temperature ** 2)

    # Hard-label loss: standard cross-entropy against ground truth.
    hard_loss = F.cross_entropy(student_logits, labels)

    return alpha * soft_loss + (1 - alpha) * hard_loss

# Training step (teacher frozen, in eval mode):
# with torch.no_grad():
#     teacher_logits = teacher(inputs)
# student_logits = student(inputs)
# loss = distillation_loss(student_logits, teacher_logits, labels)
# loss.backward(); optimizer.step()
```
