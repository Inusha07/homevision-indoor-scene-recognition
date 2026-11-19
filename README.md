# HomeVision: Indoor Scene Recognition for Smart Homes

COMP50056 Advanced Machine Learning | Individual Assignment

## Overview
HomeVision is a deep learning system that recognises room types from images so a smart home can adjust lighting, HVAC and energy use automatically. It classifies five rooms: bathroom, bedroom, kitchen, living room and office.

## Dataset
MIT Indoor Scenes (Kaggle: itsahmad/indoor-scenes-cvpr-2019). 2,388 images after removing 20 duplicates, split 70/15/15 (stratified).
The dataset is not included in this repository.

## Models
- **Custom CNN:** 4 convolution blocks, batch normalisation, dropout, global average pooling, trained from scratch.
- **ResNet50:** ImageNet transfer learning. A new head was trained first, then the last 30 layers were fine-tuned at a low learning rate.

## Results (test set, 359 images)
| Model | Accuracy | Macro-F1 |
|---|---|---|
| Custom CNN | 49.3% | 0.454 |
| ResNet50 (fine-tuned) | 85.0% | 0.802 |

Grad-CAM was used to check that ResNet50 focuses on meaningful objects.

## How to run
1. Open the notebook in Google Colab and set the runtime to GPU.
2. Add `KAGGLE_USERNAME` and `KAGGLE_KEY` in Colab Secrets.
3. Run all cells.

## Tools
Python, TensorFlow/Keras, scikit-learn, Google Colab.
