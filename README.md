# Deep Learning for Image Classification

Four reproducible PyTorch studies of convolutional architecture design, model efficiency, gradient flow, and transfer learning. Each study includes the complete experiment notebook, saved training output, validation analysis, and a final test evaluation.

| Study | Dataset | Main question | Selected model | Reported test result |
| --- | --- | --- | --- | --- |
| [Efficient CNNs](fashion-mnist-efficient-cnn/) | Fashion-MNIST | How much can a classifier shrink while retaining accuracy? | Compact CNN with 2×2 adaptive pooling | 88.19% accuracy |
| [CNN architectures](cifar10-cnn-architectures/) | CIFAR-10 | How do AlexNet-like, VGG-like, and Inception-like designs compare? | Inception with parallel branches | 77.91% accuracy |
| [Feature reuse](cifar10-residual-dense-networks/) | CIFAR-10 | How do plain, residual, and dense connections affect training? | DenseNet, growth rate 12 | 77.34% accuracy |
| [Transfer learning](flowers102-transfer-learning/) | Oxford Flowers 102 | When does ImageNet pretraining help with limited labeled data? | ResNet18, full-data fine-tuning | 77.15% accuracy; 0.7739 macro-F1 |

These values come from saved notebook output. They have not been independently rerun in this repository. The studies use different selection rules and datasets, so the test scores are not a common leaderboard.

## Methods

- Fixed random seed (`42`) and held-out validation sets for model selection.
- Checkpoints selected by minimum validation loss; peak validation accuracy is reported separately.
- Test sets evaluated only after a model was selected.
- Parameter counts, runtime measurements, learning curves, and class-level errors included where relevant.
- All experiments use PyTorch and torchvision. Dataset downloads occur when the notebooks run.

## Run locally

Use Python 3.10+ and install a compatible PyTorch/torchvision pair for your CPU or CUDA setup from the [official PyTorch installation guide](https://pytorch.org/get-started/locally/). Then install the remaining dependencies:

```bash
python -m pip install -r requirements.txt
jupyter lab
```

Open a study's `analysis.ipynb` and run cells from top to bottom. Each notebook downloads its dataset into a local `data/` directory. The Flowers 102 study also downloads pretrained ResNet18 weights. A GPU is recommended for full training, especially for the Flowers 102 experiments. Training time and measured inference latency depend on hardware.

The notebooks retain saved outputs so the reported results can be inspected without rerunning training. Rerunning will replace those outputs with results from the current environment.

## Repository layout

Each study directory contains `analysis.ipynb` and a short project README. Source briefs, downloaded datasets, and model checkpoints are excluded from the repository.
