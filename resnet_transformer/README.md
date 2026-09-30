# ResNet-transformer

`model.py` retains the ResNet18 grayscale frame encoder and two temporal
transformer variants present in the development code. Their forward operations
are preserved; personal-name class prefixes were replaced with descriptive
names. Neither data loading nor training is included.

| Class | Source behavior |
| --- | --- |
| `ResNetTransformerModel` | Legacy positional encoding, then temporal mean pooling |
| `CenterFrameResNetTransformerModel` | Temporal positional encoding, then center-frame selection |

The legacy positional encoder indexes the first tensor axis even though the
transformer receives batch-first tensors. It is retained as implemented for
checkpoint comparison; it is not silently corrected here. The center-frame
variant is used by the later clip-based model factory. The exact variant behind
each paper result still needs confirmation.

Input: `[batch, frames, 1, height, width]`. Output: two logits ordered
`[nonscratching, scratching]`. The model itself does not sample or pad frames.

Install this folder's `requirements.txt` in a dedicated environment. Example
construction from the repository root with the clip-based factory defaults:

```python
from resnet_transformer import CenterFrameResNetTransformerModel

model = CenterFrameResNetTransformerModel(
    num_classes=2, d_model=256, nhead=8, num_layers=4,
    dim_feedforward=512, dropout=0.3,
)
```

Construction requests torchvision's ResNet18 pretrained weights. A task-trained
checkpoint and its matching constructor values are needed for predictions.
