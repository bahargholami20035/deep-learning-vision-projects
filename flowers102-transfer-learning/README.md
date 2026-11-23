# Transfer Learning with Limited Flower Images

This study compares three ResNet18 training strategies on Oxford Flowers 102: random initialization, ImageNet feature extraction with a frozen backbone, and partial fine-tuning. Each strategy is evaluated with five or ten training images per class, producing six controlled experiments.

The official dataset partitions remain separate. The small training set contains 510 images and is a subset of the 1,020-image full training set; validation contains 1,020 images. Images are resized to 192×192. Checkpoints are selected by minimum validation loss, and the final strategy is chosen using validation macro-F1 and training cost before the test evaluation.

**Reported result:** full-data fine-tuning reached **77.15% test accuracy**, **0.7739 test macro-F1**, and **0.8509 test loss** at its epoch 9 checkpoint. These are saved notebook results, not a fresh run.

Open [analysis.ipynb](analysis.ipynb) to inspect the full experiment.
