# Solution_G_Naveen_Raaghavendran_Emtensor
Brain MRI Segmentation using U-Net

# Brain MRI Segmentation using U-Net

## Project Overview
This project focuses on automated brain segmentation using deep learning models. Initially, the nnU-Net framework was explored but was found to be infeasible due to GPU limitations. Instead, a custom U-Net model was implemented using the MONAI library to achieve segmentation.

## Challenges Faced
- **GPU Limitations**: The environment lacked GPU availability (`torch.cuda.is_available()` returned `False`), making training significantly slower.
- **Data Preprocessing**: Handling `.nii` files efficiently and ensuring correct input dimensions for the model.
- **Model Selection**: Due to computational constraints, a lighter version of U-Net was preferred over nnU-Net.
- **Statistical Analysis**: Assessing segmentation outputs quantitatively to validate performance.

## Implementation Steps
### 1. Dataset Processing
- Loaded `.nii` files using NiBabel.
- Normalized image data and ensured correct tensor dimensions.
- Used `DataLoader` to batch-process images efficiently.

### 2. Model Selection
- Implemented a **3D U-Net** using MONAI.
- Configured `in_channels=1`, `out_channels=1`, and `spatial_dims=3`.

### 3. Training
- Used **Binary Cross Entropy Loss** with an **Adam optimizer**.
- Adjusted input dimensions to be multiples of 16 for U-Net compatibility.
- Trained on CPU due to hardware limitations, requiring reduced batch sizes.

### 4. Inference & Visualization
- Applied segmentation on test images.
- Used `matplotlib` to visualize mid-slices of 3D outputs.

### 5. Statistical Analysis
- Computed segmented volume differences across sample groups.
- Performed a **T-test** to analyze statistical significance.
- Visualized distribution using histograms and box plots.

## Installation & Setup
To run the code, install the required dependencies:
```sh
pip install torch torchvision monai nibabel scipy matplotlib
```

## Running the Code
1. Clone the repository.
2. Install the required dependencies.
3. Run the provided Jupyter Notebook (`.ipynb` file) for step-by-step execution.

The complete implementation is available as an **IPython Notebook (ipynb file)** for reproducibility.


