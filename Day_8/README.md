# Day 8 – Weight Initialization (Zero, Small, Large, Xavier, He)

This experiment demonstrates why weight initialization is critical for training neural networks and how different initialization strategies affect activations and gradient flow.

The goal is to understand what happens when weights are initialized poorly and why Xavier (Glorot) and He initialization were designed.

---

## Experiment Overview

A synthetic input matrix was generated with:
- 1000 samples
- 1000 input features (fan_in = 1000)

The same input data was passed through a single hidden layer using different weight initialization strategies.  
For each strategy, the following statistics were observed:
- Mean and standard deviation of pre-activation values (`z`)
- Mean and standard deviation of activations
- Mean and standard deviation of gradients

This allows direct comparison of signal strength and gradient behavior.

---

## Zero Initialization

All weights were initialized to zero.

Observed behavior:
- Pre-activation values (`z`) were exactly zero
- Activations were zero for all neurons
- Gradients were identical for every neuron

Because all neurons start with the same weights, they produce identical outputs and receive identical gradients. As a result, neurons never differentiate and the network behaves like a single neuron.

This is known as the **symmetry problem**, and learning fails completely.

---

## Small Initialization

All weights were initialized to very small values (0.0001).

Observed behavior:
- Pre-activation values were extremely small
- Activations were close to zero
- Gradients existed but were very weak

Although symmetry is technically broken, the signal magnitude is too small. As the network depth increases, signals and gradients shrink further, causing learning to slow down drastically.

This leads to **vanishing gradients**.

---

## Large Initialization

All weights were initialized to large values (1.0).

Observed behavior:
- Pre-activation values had very large variance
- `tanh` activations saturated near ±1
- Gradients became close to zero or unstable

When activations saturate, their derivatives approach zero. This blocks gradient flow and prevents effective learning. In some cases, gradients may also explode, causing unstable training.

This results in **exploding or vanishing gradients**.

---

## Xavier (Glorot) Initialization

Weights were initialized using the Xavier method:

\[
W \sim \mathcal{N}\left(0, \frac{1}{fan\_in}\right)
\]

This strategy is designed for `tanh` and `sigmoid` activations.

Observed behavior:
- Pre-activation variance was close to 1
- Activations were well-distributed and centered around zero
- Gradients were strong and stable

Xavier initialization keeps the signal magnitude balanced across layers, preventing both vanishing and exploding gradients. This allows learning to begin smoothly and remain stable.

This is the preferred initialization for `tanh` and `sigmoid` networks.

---

## He Initialization

Weights were initialized using the He method:

\[
W \sim \mathcal{N}\left(0, \frac{2}{fan\_in}\right)
\]

This strategy is designed for `ReLU` and `Leaky ReLU` activations.

Observed behavior:
- Pre-activation variance was slightly higher than Xavier
- ReLU zeroed approximately half of the activations
- Remaining activations retained healthy magnitude
- Gradients flowed through active neurons effectively

Because ReLU discards negative values, He initialization compensates by allowing slightly larger variance. This keeps enough neurons active and prevents dead ReLU units.

This is the preferred initialization for ReLU-based networks.

---

## Final Comparison Summary

Zero initialization fails due to symmetry.  
Small initialization leads to vanishing gradients.  
Large initialization causes saturation and unstable training.  
Xavier initialization maintains stable signals for `tanh` and `sigmoid`.  
He initialization maintains healthy gradient flow for `ReLU`.

---

## Key Takeaways

Weight initialization determines whether learning can even begin.  
Poor initialization can completely break training before optimization starts.  
Xavier and He initialization are mathematically designed to preserve signal and gradient flow across layers.  
Choosing the correct initialization depends on the activation function used.

---

## Conclusion

This experiment shows that successful neural network training is not only about optimization algorithms but also about how weights are initialized. Xavier and He initialization solve fundamental problems that arise from depth and high dimensionality, making deep learning practical and stable.

---

## Next Step

Study **regularization techniques** to understand how neural networks generalize and avoid overfitting.
