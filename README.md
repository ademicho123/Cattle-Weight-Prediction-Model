# Cattle Weight Prediction Model

This project aims to build a deep learning model to predict cattle weight based on images. The model utilizes Convolutional Neural Networks (CNN) for image-based regression to estimate the weight of cattle from the provided images.

## Project Structure

Cattle-Weight-Prediction-Model/ ├── dataset/ │ ├── Pixel/ │ │ ├── B2/ │ │ ├── B3/ │ │ └── B4/ │ └── Vector/ │ ├── B2/ │ ├── B3/ │ └── B4/ ├── cattle_weight_model.ipynb └── README.md

### Dataset Folder Structure

- `Pixel/`: Contains subdirectories for datasets B2, B3, and B4 with images of the cattle.
  - **B2, B3, B4**: Subdirectories that include `Side` and `Rear` views of the cattle.
- `Vector/`: Contains vector-based keypoints data for different views of cattle, which might be used for enhancing the model in the future.
  
### Filename Conventions

- **B2 & B3**: `<id>_<side>/<rear>_<manual-weight>_<sex>.<extension>`
- **B4**: `<id>_<batchid>-<subbatch-id>_<side>/<rear>_<manual-weight>_<sex>.<extension>`

### Model Architecture

The CNN-based model is defined in `cattle_weight_model.ipynb`. The architecture includes:

1. **Convolutional Layers**: For feature extraction from images.
2. **MaxPooling Layers**: To reduce spatial dimensions.
3. **Dense Layers**: For regression and prediction of cattle weight.
4. **Regularization**: Dropout and L2 regularization to combat overfitting.

### Key Features

- **Data Augmentation**: Applied to improve model generalization.
- **Early Stopping**: Used to stop training when the validation loss starts to increase, preventing overfitting.
- **Metrics**: Model uses Mean Absolute Error (MAE) and Mean Squared Error (MSE) as performance metrics.
  
## Usage

### Prerequisites

Ensure you have the following dependencies installed:

```bash
pip install tensorflow numpy scikit-learn matplotlib ipywidgets
