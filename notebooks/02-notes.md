# :basketball: Notes and conclusions of `02-trainBase.ipynb`

## Dataset
The dataset used in this notebook can be found in `data/basketball.yolov8`.

## Model setup
YOLOv8n was selected as model for efficiency and reproducibility, with fixed hyperparameters to ensure fair comparison across experiments.

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
- The YOLOv8n model was trained using the Ultralytics YOLO API
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
All evaluation metrics are exported to a CSV file called `base_metrics.csv` inside the `results`-folder.
