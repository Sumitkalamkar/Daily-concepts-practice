# Day 13 – Adam Optimizer (From Scratch)

This experiment implements the Adam optimizer from scratch and applies it to a real-world binary classification task. The goal is to understand how Adam combines Momentum and RMSProp to achieve fast and stable convergence.

---

## Objective

- Implement the Adam optimizer manually using NumPy
- Apply Adam to a real dataset using logistic regression
- Observe convergence behavior and final loss
- Prepare for optimizer comparison in the next step

---

## Dataset

- **Name:** Breast Cancer Wisconsin Dataset
- **Task:** Binary Classification
- **Number of Features:** 30
- **Preprocessing:** Feature scaling using StandardScaler

---

## Model Details

- Logistic Regression (from scratch)
- Sigmoid activation function
- Binary Cross-Entropy loss function
- No external optimization libraries used

---

## Adam Optimizer Overview

Adam (Adaptive Moment Estimation) combines:
- **Momentum** → remembers gradient direction
- **RMSProp** → adapts learning rate using gradient magnitude

For each parameter, Adam maintains:
- First moment (mean of gradients)
- Second moment (mean of squared gradients)

Bias correction is applied using the iteration count to ensure stable updates during early training.

---

## Mathematical Formulation

- **First moment update**
# m = β₁ · m + (1 − β₁) · g

 **Second moment update**
# v = β₂ · v + (1 − β₂) · g²


**Bias correction**
# m̂ = m / (1 − β₁ᵗ)
# v̂ = v / (1 − β₂ᵗ)


**Parameter update**
# w = w − α · m̂ / (√v̂ + ε)




---

## Hyperparameters Used

- Learning Rate (α): 0.01
- β₁ (Momentum decay): 0.9
- β₂ (Variance decay): 0.999
- ε (Numerical stability): 1e-8
- Epochs: 1000

---

## Training Results

- **Epoch 500 Loss:** 0.057925
- **Epoch 1000 Loss:** 0.048864
- **Final Training Loss:** **0.048864**

The loss decreases smoothly, indicating stable and efficient convergence.

---

## Observations

- Adam converges faster than earlier optimizers studied
- Updates are stable with no oscillations or NaN values
- Adaptive learning rates reduce sensitivity to hyperparameters
- Bias correction improves early-stage learning
- Adam handles steep and flat regions effectively

---

## Key Takeaways

- Adam combines direction (Momentum) and scale (RMSProp)
- Automatically adapts learning rates per parameter
- Requires minimal tuning
- Widely used as a default optimizer in deep learning

---

## Conclusion

This experiment demonstrates that Adam provides fast, stable, and reliable optimization when implemented from scratch. The low final loss confirms Adam’s effectiveness on a real-world dataset.

---

## Next Step

- Compare Gradient Descent, Momentum, RMSProp, and Adam under identical training conditions.


