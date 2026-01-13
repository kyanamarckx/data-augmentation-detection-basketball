# :basketball: Notes and conclusions of `03-trainAugmentations.ipynb`

## Datasets
The datasets used in this notebook can be found in `data/basketball-augmented.yolov8`.

Augmentations are grouped into three distinct categories:
- Geometric transformations
- Color space modifications
- Kernel based filters

Each augmented dataset includes the original images to avoid training on augmented data only.

## Model setup
YOLOv8n was used across all experiments. Identical hyperparameters were applied for all runs to ensure comparability and reproducibility.

### Fixed parameters
- **Image size:**
  - 640
- **Batch size:**
  - 16
- **Epochs:**
  - 100
- **Seed:**
  - 42

## Training
- The YOLOv8n models were trained separately per category using the Ultralytics YOLO API
- Built-in augmentation is explicitly disabled

## Evaluation
- Evaluation is performed on a held-out test split
- The collected metrics are:
  - mAP50
  - mAP50-95
  - Precision
  - Recall
  - Fitness
  - Preprocessing time (ms)
  - Inference time (ms)
  - Postprocessing time (ms)

## Outputs
All evaluation metrics are exported to a CSV file called `augmented_metrics.csv` inside the `results`-folder.
