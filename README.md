# 3D Mesh Objects Segmentation
![3D segmented mesh arch](https://user-images.githubusercontent.com/150384965/281849484-cd6b2c49-06da-459a-90d6-5d73adc22f81.png)

## Introduction

This Python project utilizes diffusion models for the segmentation of 3D dental arches mesh objects. The script is structured into nine sequential steps, providing a comprehensive guide for users.

## Steps

### Step 1: Mount Google Drive

This step involves utilizing the `google.colab` module to mount your Google Drive account. By running `drive.mount('/content/drive')`, the code facilitates access to files stored on Google Drive within the Colab environment, essential for data and model accessibility.

### Step 2: Clone a Git repository

This section clones a Git repository from the specified URL (https://github.com/nmwsharp/diffusion-net.git) using the `!git clone` command. The repository appears to contain essential source code required for subsequent script execution.

### Step 3: Install Python dependencies

This step installs necessary Python packages through `pip install`. The packages include `trimesh`, `plyfile`, `polyscope`, `potpourri3d`, `python-utils`, `robust-laplacian`, `threadpoolctl`, `tqdm`, and `typing-extensions`, supporting various data processing and machine learning operations.

### Step 4: Data Augmentation

This section defines data augmentation functions for 3D models, including random rotations, scalings, and translations. The `data_augmentation` function applies these augmentations to the input models, saving the augmented models in OBJ format and the labels in JSON format.

### Step 5: Load and Prepare the Dataset

This step involves loading and preparing the dataset from OBJ and JSON files. The models and labels are loaded from specified directories, with model vertices normalized for centering and scaling. Geometric operators such as Laplacian matrices are calculated, and the data is stored in lists for machine learning.

### Step 6: Train the Model

The script trains a segmentation model named "DiffusionNet" on the prepared dataset. Model configuration includes parameters like segmentation classes, input features, and hidden layer width. Training occurs for a specified number of epochs using negative log-likelihood loss for backpropagation. Model performance is evaluated on the test dataset.

### Step 7: Visualize the Performance

This step generates visualizations of the model's performance over epochs using Plotly. Accuracy and loss curves are plotted separately for better comprehension.

### Step 8: Test on a 3D Object

The trained model is tested on a specific 3D object loaded from a specified file. Geometric operators are calculated, and the model predicts segmentation labels for each face of the object. Predicted labels are used to color the 3D object, visualized using Plotly.

### Step 9: Save the Trained Model

Finally, the trained model is saved to a specified file using `torch.save`.


## Additional Information

- The code is written in Python using the PyTorch deep learning library.
- Trained and tested on a dataset of dental arches : https://drive.google.com/file/d/1K5VoGXuom7LiambwXV2BCr2ZCfze22cq  .
- Applicable for segmenting 3D mesh objects of various shapes and sizes.
