# :basketball: Notes and conclusions of `01-createAugmentations.ipynb`

## Augmentations
The following augmentation categories were defined and generated as separate datasets:
- **Geometric augmentations**, focusing on spatial transformations such as horizontal flip, rotation and scaling.
- **Color space augmentations**, altering brightness and contrast, saturation and color shift.
- **Kernel-based augmentations**, including Gaussian blur and motion blur.

### Dataset
Each augmented dataset includes:
- The original images
- One augmented variant per original image,
resulting in a balanced dataset size across all augmentation types

All augmentations were applied offline (prior to training) and stored in dedicated folders. This avoids randomness during training and guarantees that each model is trained on exactly the same data across runs.
