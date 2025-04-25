# CNN Histopathologic Cancer Detection Kaggle Mini-Project

This repository contains my submission for the Kaggle Histopathologic Cancer Detection competition as part of a peer-graded assignment. The project involves binary image classification to identify metastatic cancer in 96x96 pixel image patches using convolutional neural networks (CNNs).

## Project Overview
- **Objective**: Build and compare a custom CNN and VGG16 model to classify histopathologic images, evaluated by AUC on Kaggle.
- **Dataset**: ~220,000 training images, ~57,000 test images, 96x96 pixels, RGB, `.tif` format.
- **Models**:
  - Custom CNN: Lightweight with 3 convolutional layers, batch normalization, and dropout.
  - VGG16: Transfer learning with ImageNet weights (or random weights due to network issues).
- **Results**: Custom CNN AUC ~0.82, VGG16 AUC ~0.7 (random weights due to network issues).

## Repository Structure
- `notebooks/`: Jupyter notebook(s) with the project code.
  - `w3-cnn.ipynb`: Main notebook with EDA, training, results, and submission.
- `outputs/`: Output files.
  - `submission.csv`: Kaggle submission file.
- `models/`: Saved models.
  - `custom_cnn.h5`: Custom CNN model.
  - `vgg16.h5`: VGG16 model.

## How to Run
- Open `notebooks/w3-cnn.ipynb` in Kaggle or Jupyter Notebook.
- Ensure the dataset is available at `/kaggle/input/histopathologic-cancer-detection/`.
- Run all cells to reproduce the training, predictions, and results.
- Note: VGG16 requires internet to download pretrained weights (`Notebook Options > Internet On` in Kaggle).

## Challenges
- Data exhaustion in Epoch 2 limited training for both models.
- Network issues prevented VGG16 pretrained weights, lowering AUC to ~0.7.

## Future Improvements
- Enable internet for VGG16 pretrained weights.
- Adjust generator steps to prevent data exhaustion.
- Add class weights for imbalance, fine-tune VGG16.
