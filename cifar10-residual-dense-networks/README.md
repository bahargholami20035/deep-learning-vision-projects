# Residual and Dense Feature Reuse on CIFAR-10

This study compares a plain convolutional network, a small residual network, and two dense networks built from custom PyTorch blocks. It examines projection shortcuts, tensor dimensions, parameter budgets, training curves, and gradient norms at several points in training.

The 50,000 CIFAR-10 training images are split into 45,000 training and 5,000 validation images with seed 42. Four models are trained for ten epochs under shared settings. Checkpoints use minimum validation loss. Gradient measurements use the same fixed batch in evaluation mode without an optimizer step.

**Reported result:** `DenseNet-k12` was selected with **76,858 parameters** and reached **77.34% test accuracy** and **0.6605 test loss**. In this recorded run, the residual model did not outperform the plain model on validation accuracy. These are saved notebook results, not a fresh run.

Open [analysis.ipynb](analysis.ipynb) to inspect the full experiment.
