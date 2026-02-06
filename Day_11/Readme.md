# Day 11 – Gradient Descent vs Momentum Optimization

This experiment compares standard Gradient Descent with Gradient Descent using Momentum to understand how momentum improves optimization speed and stability.

---

## Objective

The objective of this experiment is to observe how momentum affects convergence behavior and final loss when training a model using gradient-based optimization.

---

## Experiment Setup

- Model: Logistic Regression (implemented from scratch)
- Dataset: Breast Cancer Wisconsin Dataset
- Feature Scaling: StandardScaler
- Loss Function: Binary Cross-Entropy
- Optimization Methods:
  - Plain Gradient Descent
  - Gradient Descent with Momentum
- Learning Rate: Fixed and identical for both methods
- Epochs: Same number for fair comparison

---

## Results

Final training loss after optimization:

- Gradient Descent: **0.0877**
- Momentum: **0.0543**

Momentum achieved a noticeably lower final loss compared to plain Gradient Descent.

---

## Observations

- Plain Gradient Descent converges more slowly and is affected by zig-zag motion in narrow loss valleys.
- Momentum converges faster by accumulating past gradients and smoothing updates.
- With the same learning rate and number of epochs, Momentum reaches a better solution.
- Momentum reduces inefficient sideways movement and focuses updates in a consistent direction.

---

## Intuition Behind Momentum

Gradient Descent updates parameters based only on the current gradient, which can cause oscillations when gradients vary across dimensions.

Momentum introduces a velocity term that remembers recent update directions. This memory helps the optimizer continue moving in a useful direction instead of constantly reacting to small gradient changes.

As a result:
- Oscillations are reduced
- Convergence is faster
- Final loss is lower

---

## Key Takeaways

- Momentum improves optimization efficiency without changing the model or data.
- It accelerates learning in consistent directions and dampens noise.
- Momentum is especially effective in narrow or ill-conditioned loss landscapes.
- This experiment confirms that Momentum outperforms plain Gradient Descent under identical conditions.

---

## Conclusion

Gradient Descent with Momentum provides faster and more stable convergence than plain Gradient Descent.  
The lower final loss achieved by Momentum demonstrates its effectiveness in practical optimization scenarios.

Momentum is a foundational concept used in many advanced optimizers such as Adam.

---

## Next Step

Extend this comparison to adaptive optimizers such as RMSProp and Adam to study automatic learning rate adjustment.
