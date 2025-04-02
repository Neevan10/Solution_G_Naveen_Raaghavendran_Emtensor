# Solution_G_Naveen_Raaghavendran_Emtensor
# Brain Tumor Segmentation using UNet

## Project Overview
This project focuses on automated brain tumor segmentation using deep learning models. Initially, we attempted to use `nnUNet`, but due to GPU limitations (torch.cuda being `False`), we switched to a pretrained `UNet` model from MONAI. The project includes dataset preprocessing, model training, inference, and statistical analysis to compare segmented volumes.

## Dataset
The dataset used is named **brats_dataset**. Please download and place it accordingly as mentioned in the `.ipynb` file.

## Implementation Steps
1. **Data Loading & Preprocessing:**
   - Used `nibabel` to load `.nii` files.
   - Normalized images and converted them to tensors.
   - Created a custom `Dataset` class and `DataLoader` for batching.

2. **Model Selection:**
   - Initially attempted `nnUNet` but switched to `UNet` from MONAI due to GPU constraints.
   - The model was trained using **Adam optimizer** and **BCEWithLogitsLoss**.

3. **Training & Evaluation:**
   - Training loop with batch normalization and interpolation for resizing.
   - Model performance analyzed through segmentation output.

4. **Inference:**
   - Segmentation applied to new samples.
   - Plots generated to visualize segmentation outputs.

5. **Statistical Analysis:**
   - Compared segmented tumor volumes across samples.
   - **T-test** performed to analyze variations.
   - Graphs plotted for better visualization.

## Installation & Setup
To run this project, install the necessary dependencies:

```sh
pip install torch torchvision torchaudio monai nibabel scipy matplotlib numpy
```

Run the Jupyter Notebook (`.ipynb` file) to execute the steps as described.

## Code Availability
The complete implementation, including preprocessing, training, and analysis, is available as a **Jupyter Notebook (`.ipynb`) file**. Follow the steps mentioned to replicate results.

---




