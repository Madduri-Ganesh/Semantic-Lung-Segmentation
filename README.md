# U-Net with Resnet34 Backbone for Semantic Lung Segmentation in Chest X-rays

## Overview
This project implements a **semantic lung segmentation** model using a **U-Net** architecture with a **ResNet34** encoder pre-trained on ImageNet. The model is designed to perform binary segmentation on grayscale chest X-ray images, identifying lung regions.

## Model Architecture
- **Base Architecture**: U-Net
- **Encoder**: ResNet34 (pre-trained on ImageNet)
- **Input**: Grayscale images
- **Output**: Binary segmentation masks
- **Library**: segmentation_models_pytorch

## Dataset
- **Total Datapoints**: 60
- **Training Set**: 50 samples
- **Test Set**: 10 samples
- **Image Size**: 128x128 pixels
- **Format**: Grayscale images and corresponding binary masks

## Data Preprocessing
- **Resizing** of images and masks to 128x128 pixels
- **Conversion** to PyTorch tensors
- Custom `SegmentationDataset` class for handling image-mask pairs

## Training Details
- **Optimizer**: Adam
- **Learning Rate**: 0.001
- **Loss Function**: Binary Cross-Entropy with Logits Loss
- **Epochs**: 100
- **Batch Size**: 32
- **Validation**: Performed after each epoch

## Evaluation
- **Metric**: Intersection over Union (IoU)
- **Threshold**: 0.5 for creating binary masks from predictions
- **Visualization**: Function provided to display original image, true mask, and predicted mask with IoU score

## Results
The model achieved impressive performance on the test set:
- **Average IoU Score**: 0.9119

This high IoU score indicates excellent segmentation accuracy, with the model's predictions closely matching the ground truth lung masks.
