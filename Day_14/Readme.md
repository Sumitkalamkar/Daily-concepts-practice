# Day 14 – Optimizer Comparison (GD vs Momentum vs RMSProp vs Adam)

This experiment compares four optimization algorithms implemented from scratch on the same dataset, using identical training conditions. The goal is to analyze convergence behavior and final training loss to understand practical differences between optimizers.

---

## Objective

- Compare Gradient Descent, Momentum, RMSProp, and Adam
- Use identical model, dataset, and hyperparameters
- Evaluate final training loss
- Understand practical optimizer behavior

---

## Dataset

- **Name:** Breast Cancer Wisconsin Dataset
- **Task:** Binary Classification
- **Features:** 30
- **Preprocessing:** StandardScaler applied
- **Model:** Logistic Regression (implemented from scratch)
- **Loss Function:** Binary Cross-Entropy
- **Epochs:** 1000
- **Learning Rate:** Same for all optimizers

---

## Final Loss Results

Gradient Descent : 0.109785  
Momentum         : 0.109307  
RMSProp          : 0.019651  
Adam             : 0.048852  

---

## Observations

### 1️⃣ Gradient Descent
- Slow convergence
- Higher final loss
- Sensitive to learning rate
- Oscillates in narrow valleys

### 2️⃣ Momentum
- Slight improvement over GD
- Smoother updates
- Faster convergence than GD
- Still uses fixed learning rate

### 3️⃣ RMSProp
- Achieved the lowest final loss
- Stable updates
- Adaptive learning rates per parameter
- Handles steep gradients effectively

### 4️⃣ Adam
- Fast and stable convergence
- Combines Momentum + RMSProp
- Achieved lower loss than GD and Momentum
- Slightly higher loss than RMSProp in this experiment

---

## Key Insights

- Adaptive learning rate methods (RMSProp, Adam) significantly outperform fixed learning rate methods (GD, Momentum).
- Momentum improves speed but does not adapt step sizes.
- RMSProp performed best in this particular setup.
- Adam did not achieve the lowest loss here, showing that it is not always the best optimizer in every scenario.
- Optimizer performance depends on dataset, learning rate, and training duration.

---

## Important Learning

Optimization performance is context-dependent. While Adam is often the default choice in deep learning, RMSProp can outperform it under certain conditions.

This experiment demonstrates that:

- Gradient Descent is simple but inefficient.
- Momentum improves direction control.
- RMSProp improves stability via adaptive scaling.
- Adam combines both but may not always produce the lowest final loss.

---

## Conclusion

Among all tested optimizers, RMSProp achieved the lowest training loss under identical conditions. This comparison highlights the importance of understanding optimizer mechanics rather than assuming one optimizer is universally superior.

---

## Next Steps

- Plot convergence curves for visual comparison
- Compare test accuracy alongside training loss
- Experiment with different learning rates
- Analyze generalization performance
