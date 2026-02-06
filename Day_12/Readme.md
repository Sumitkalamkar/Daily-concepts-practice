# Day 12 – Understanding and Implementing RMSProp Optimizer from Scratch

This day focuses on deeply understanding the RMSProp optimization algorithm by implementing it from scratch and applying it to a real-world dataset. The goal is not just to run the optimizer, but to understand **why RMSProp exists**, **what problem it solves**, and **how it improves learning compared to standard Gradient Descent**.

---

## Background and Motivation

In previous days, standard Gradient Descent and Momentum-based optimization were implemented and analyzed. While these methods work, they suffer from important limitations:

- A single learning rate is used for all parameters
- Parameters with large gradients can cause unstable updates
- Parameters with small gradients may learn very slowly
- Training can become noisy or oscillatory in uneven loss landscapes

These issues motivated the need for an optimizer that can **adapt learning rates automatically for each parameter**.

RMSProp was introduced to solve exactly this problem.

---

## What RMSProp Does (Conceptual Explanation)

RMSProp stands for **Root Mean Square Propagation**.

The key idea behind RMSProp is simple:

> Instead of using the same learning rate for all parameters, RMSProp scales the learning rate for each parameter based on how large its recent gradients have been.

This is achieved by maintaining an **exponential moving average of squared gradients**.

- If a parameter consistently receives large gradients, RMSProp reduces its update size
- If a parameter receives small gradients, RMSProp allows larger updates
- This leads to more stable and balanced learning

RMSProp does **not** remember the direction of gradients (like Momentum).  
It only remembers their **magnitude**.

---

## Mathematical Formulation

For each parameter, RMSProp maintains a cache variable `s`:

### Exponential Moving Average of Squared Gradients

## s = β · s + (1 − β) · g²


Where:
- `g` is the current gradient
- `β` is the decay rate (typically 0.9)

### Parameter Update Rule

## w = w − (α / (√s + ε)) · g



Where:
- `α` is the learning rate
- `ε` is a small constant added for numerical stability

The denominator ensures that parameters with large gradient history take smaller steps.

---

## Dataset and Model

For this experiment:

- Dataset: **Breast Cancer Wisconsin Dataset**
- Task: Binary Classification
- Model: Logistic Regression (implemented completely from scratch)
- Feature Scaling: StandardScaler
- Loss Function: Binary Cross-Entropy Loss
- Optimizer: RMSProp

No high-level ML libraries were used for optimization.  
All computations were implemented manually using NumPy.

---

## Implementation Details

During implementation, several important practical issues were addressed:

1. **Label Reshaping**
   - Labels were reshaped to column vectors `(n, 1)` to avoid broadcasting errors.

2. **Numerical Stability**
   - A small epsilon value (`1e-8`) was added inside logarithms to avoid `log(0)` errors.
   - This prevents `NaN` values during training.

3. **Per-Parameter State**
   - Separate RMSProp cache values were maintained for weights and bias.

These steps are essential in real-world deep learning systems.

---

## Training Outcome

After training the model using RMSProp, the following result was obtained:

## Final Loss (RMSProp): 0.0220


This loss value is significantly lower than what is typically achieved using:
- Plain Gradient Descent
- Gradient Descent with Momentum

A loss around `0.02` for binary cross-entropy indicates:
- Strong convergence
- Confident and accurate predictions
- Stable optimization behavior

---

## Observations and Analysis

From this experiment, the following observations were made:

- RMSProp converges smoothly without oscillations
- Adaptive learning rates prevent unstable updates
- Training is less sensitive to learning rate choice
- RMSProp reaches a better minimum in the same number of epochs
- Numerical stability techniques are crucial in practice

This confirms the theoretical motivation behind RMSProp.

---

## Key Learnings

- RMSProp adapts learning rates per parameter automatically
- It stabilizes learning when gradients vary in magnitude
- It prevents exploding updates without slowing down learning
- RMSProp is especially effective for noisy or uneven loss surfaces
- Proper implementation details (shapes, epsilon, scaling) matter a lot

---

## Conclusion

RMSProp is a powerful optimization algorithm that improves training stability by scaling updates using historical gradient magnitudes. Through this hands-on implementation and experimentation, RMSProp was shown to outperform standard Gradient Descent methods on a real dataset.

This experiment builds a strong foundation for understanding more advanced optimizers such as **Adam**, which combines Momentum and RMSProp.

---

## Next Steps

- Implement Adam optimizer from scratch
- Compare Gradient Descent, Momentum, RMSProp, and Adam
- Visualize convergence curves for all optimizers
- Study optimizer behavior in deeper neural networks
