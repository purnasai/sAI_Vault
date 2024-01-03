Reproducibility of Deep learning models in accuracy or across other metrics like losses change in Different runs based on the Environments used, software application, hardware infrastructure.

Though it is not completely possible to reproduce at lower level like tensors/neurons in model layers, we can reproduce the model metrics to most extent.

```python
import torch
import numpy as np
import random
from transformers import set_seed

def set_seed_everywhere(seed):
    torch.manual_seed(seed)
    torch.cuda.manual_seed_all(seed)
    np.random.seed(seed)
    random.seed(seed)
    set_seed(seed)  # For Hugging Face Transformers

def set_reproducibility(seed=42):
    set_seed_everywhere(seed)

    # Additional settings for reproducibility in PyTorch
    torch.backends.cudnn.deterministic = True
    torch.backends.cudnn.benchmark = False

    # Set environment variable for better reproducibility on CPU
    torch.set_deterministic(True)

    # Additional configurations if necessary for specific libraries or modules
    # For example, for CuDNN enabled devices, disabling CuDNN might be helpful
    # torch.backends.cudnn.enabled = False

    # You can add other settings specific to your use case here

# Usage:
set_reproducibility(seed=123)
# Your code utilizing PyTorch and Hugging Face Transformers models goes here
```
