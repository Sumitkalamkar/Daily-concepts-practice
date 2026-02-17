# Optimizer Comparison in Deep Learning (PyTorch)

## Overview

This project compares the performance of popular deep learning optimizers on the MNIST dataset using PyTorch.

We evaluate:

- SGD
- SGD with Momentum
- RMSprop
- Adam
- AdamW

The comparison includes:

- Training Loss
- Training Accuracy
- Test Accuracy
- Convergence Speed
- Training Time
- Confusion Matrix Analysis

---

## Dataset

**MNIST Handwritten Digits**
- 60,000 training images
- 10,000 test images
- 28x28 grayscale images
- 10 classes (digits 0–9)

---

## Model Architecture

Simple Feedforward Neural Network:

- Flatten Layer
- Linear (784 → 256) + ReLU
- Linear (256 → 128) + ReLU
- Linear (128 → 10)

Loss Function:

---

##  Results

###  Training Performance (5 Epochs)

| Optimizer       | Final Train Acc |
|----------------|----------------|
| SGD            | 92.58% |
| SGD + Momentum | 98.20% |
| RMSprop        | 98.80% |
| Adam           | 98.77% |
| AdamW          | 98.71% |

---

### Final Test Accuracy & Training Time

| Optimizer       | Test Accuracy | Training Time |
|----------------|--------------|--------------|
| SGD            | 93.38% | 57.28 sec |
| SGD + Momentum | 97.49% | 59.28 sec |
| RMSprop        | 97.88% | 59.84 sec |
| Adam           | 97.49% | 59.91 sec |
| AdamW          | 97.72% | 60.22 sec |

---

## Key Observations

### 1️. Convergence Speed
- SGD converges slowly.
- Momentum significantly improves convergence.
- RMSprop, Adam, and AdamW converge much faster.

### 2️. Best Test Performance
- **RMSprop achieved highest test accuracy (97.88%)**

### 3️. Generalization
- AdamW provides strong regularization through decoupled weight decay.
- Momentum improves stability compared to vanilla SGD.

### 4. Training Time
- All adaptive optimizers have similar training time.
- SGD slightly faster but much lower accuracy.

---

## Visualizations Included

- Loss vs Epoch
- Accuracy vs Epoch
- Confusion Matrix (Best Optimizer)
- Convergence Comparison

---

## How to Run

```bash
pip install torch torchvision matplotlib seaborn scikit-learn
