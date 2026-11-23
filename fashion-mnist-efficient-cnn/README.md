# Efficient CNNs for Fashion-MNIST

This study explores the tradeoff between classification accuracy and model size on ten classes of 28×28 grayscale clothing images. It starts with a convolutional baseline, compares one 5×5 filter with two 3×3 filters, investigates batch normalization and dropout on a smaller training subset, and replaces a large dense head with compact pooling-based heads.

The 60,000 original training images are split into 54,000 training and 6,000 validation images with seed 42. Models are selected by minimum validation loss; the test set is used for the final selected model. The notebook also checks feature-map shapes, receptive field, parameter counts, latency, and the classes most affected by compression.

**Reported result:** the selected compact model (`D2_Pool2_FC48`) reached **88.19% test accuracy** and **0.3262 test loss** at its epoch 7 checkpoint. These are saved notebook results, not a fresh run.

Open [analysis.ipynb](analysis.ipynb) to inspect the full experiment.
