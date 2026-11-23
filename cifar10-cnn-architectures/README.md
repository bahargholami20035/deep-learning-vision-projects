# Comparing CNN Architectures on CIFAR-10

This study implements compact AlexNet-like, VGG-like, and Inception-like networks for ten-class image classification. It compares receptive fields, branch design, parameter counts, validation performance, runtime, class-level errors, and sensitivity to a second random seed.

The 50,000 CIFAR-10 training images are split into 45,000 training and 5,000 validation images with seed 42. Five architectures are trained for ten epochs with shared optimization settings. Checkpoints are chosen by minimum validation loss. The final choice applies a 300,000-parameter limit, then considers validation accuracy and inference time.

**Reported result:** `Inception-plain` was selected with **268,842 parameters** and reached **77.91% test accuracy** and **0.6426 test loss**. These are saved notebook results, not a fresh run.

Open [analysis.ipynb](analysis.ipynb) to inspect the full experiment.
