# :basketball: Data augmentation in basketball games
> Kyana Marckx

This project focuses on analyzing the impact of different data augmentation techniques on YOLOv8n performance. 
Specifically, multiple augmentation categories are applied and saved seperately. 
YOLOv8n will be trained on 3 different versions of the same dataset: base (no augmentations applied, original dataset), augmented (geometric, color or kernel augmentations applied) and combined (combination of base and augmented datasets).
The models will all be tested on the same test set (curated from the original dataset).

## Dataset
The dataset used in this project is [Basketball Players](https://app.roboflow.com/kiejaana/basketball-players-fy4c2-dqb1n/1), obtained via Roboflow.<br>
A minimal preprocessing pipeline was applied prior to training. This pipeline consists of:
- Automatic image orientation (auto-orient),
- Resizing all images to a fixed resolution of **640 x 640 pixels**,
- Padding the remaining space with white border to preserve the original aspect ratio.

No data augmentation techniques were applied at this stage, as this dataset serves as the baseline for all experiments.

### Usage
This dataset is included in this repository as `basketball.yolov8.zip`.
Please extract this archive into the `data/` directory before running any notebooks or training scripts.

## Installations
Inside the `imports`-folder is a notebook `installations.ipynb` that contains all the installation commands for the used packages in this project. Run this file based on what packages are already installed on your device.

## 1 - Create augmentations
Notebook `01-createAugmentations.ipynb` is responsible for generating augmented versions of the original dataset. Several augmentation categories are considered; geometric transformations, color space modifications and kernel-based filters. Each augmentation category is applied in a controlled manner to enable isolated analysis of its effect. Notes and conclusions for this tep can be found in `01-notes.md`.

## 2 - Train base dataset
Notebook `02-trainBase.ipynb` trains a YOLOv8 object detection model using the original, non-augmented dataset. This model serves as the baseline against which all augmentation experiments are compared. Training is performed using fixed hyperparameters and a fixed random seed to ensure reproducibility. Notes and conclusions can be found in `02-notes.md`.

## 3 - Train augmented dataset
Notebook `03-trainAugmentations.ipynb` trains separate YOLOv8 models on datasets augmented with individual augmentation categories. All training settings are kept identical to the baseline experiment to ensure a fair comparison. This step enables direct assessment of the effect of each augmentation category on detection performance. Notes and conclusions can be found in `03-notes.md`.

## 4 - Combine base and augmented dataset
Notebook `04-combineAll.ipynb` constructs a combined dataset that includes the original images (included only once) together with all augmented variants. This step allows the investigation of potential interaction effects between different augmentation strategies. Notes and conclusions can be found in `04-notes.md`.

## 5 - Train combined dataset
Notebook `05-trainCombined.ipynb` trains a YOLOv8 model on the combined dataset containing both original and augmented data. The resulting performance is compared to both the baseline and individually augmented models to evaluate whether combining mutiple augmentation strategies improves generalizations. Notes and conclusions can be found in `05-notes.md`.

## 6 - Concatenate CSV's
Notebook `06-concatCSV.ipynb` aggregates evaluation metrics from all experiments into a consolidated CSV file. This includes overall detection metrics and runtime statistics. The combined results enable structures quantitative comparison and form the basis for visualizations and analysis in the final report. Notes and conclusions can be found in `06-notes.md`.
