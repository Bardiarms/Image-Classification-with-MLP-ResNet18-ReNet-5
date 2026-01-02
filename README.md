# MNIST Classification with MLP, LeNet-5, and ResNet-18  
## Translation Invariance Analysis

## Overview
This project implements and compares three neural network architectures for **handwritten digit classification** on the **MNIST** dataset:

- A **Multilayer Perceptron (MLP)**
- **LeNet-5**, a classic convolutional neural network
- **ResNet-18**, a deep residual network adapted for MNIST

Beyond classification accuracy, the project investigates **translation invariance** by evaluating how model predictions change when input images are spatially shifted.

---

## Models Implemented

### 1. Multilayer Perceptron (MLP)
- Fully connected neural network
- Input: flattened 28×28 images (784 features)
- Two hidden layers with ReLU and dropout
- Baseline model without spatial inductive bias

**Final accuracy:** ≥ 97%

---

### 2. LeNet-5
- Classic CNN architecture
- Uses convolution, average pooling, and sigmoid activations
- Architecture follows the original LeNet-5 specification adapted for MNIST

**Final accuracy:** ≥ 98%

---

### 3. ResNet-18 (Adapted)
- Deep residual network using skip connections
- Modified for MNIST:
  - Input channels changed from 3 → 1
  - First convolution adjusted for small images
  - Initial max-pooling removed
  - Final fully connected layer outputs 10 classes

**Final accuracy:** ≥ 99%

---

## Dataset
- **MNIST** handwritten digits
- 60,000 training images
- 10,000 test images
- Image size: 28×28 (grayscale)
- Normalized using dataset mean and standard deviation

---

## Training Setup
- Framework: **PyTorch**
- Loss function: `CrossEntropyLoss`
- Optimizer: `Adam`
- Device: CPU


---

## Translation Invariance Experiment
To evaluate robustness to spatial shifts:

1. A single test image is selected from MNIST
2. The image is shifted by varying pixel offsets (translation)
3. The digit is kept fully inside the image frame
4. The shifted images are passed through:
   - MLP
   - LeNet-5
   - ResNet-18
5. Predicted classes are compared across models

### Behaviour
- **MLP:** highly sensitive to translation
- **CNNs:** more stable predictions due to convolution and pooling
- **ResNet:** strongest robustness among the three

---

## Results Summary
- All models achieve their required accuracy thresholds
- CNN-based models significantly outperform MLP under image translation


---



## Author
**Bardia Rezaeimehr**  
Course Project – Artificial Intelligence