## Day 5 – Perceptron (Single Neuron Learning)

### Objective
To understand how a single neuron (Perceptron) learns using weights, bias, and a step activation function, and to observe learning through weight and bias updates.

---

### Problem Statement
Train a perceptron to learn the **OR gate**, which is a linearly separable problem.

| Input (x1, x2) | Output |
|----------------|--------|
| (0, 0) | 0 |
| (0, 1) | 1 |
| (1, 0) | 1 |
| (1, 1) | 1 |

---

### Model Used
A **single perceptron** with:
- Randomly initialized weights
- Bias term
- Step activation function

Mathematical form:
\[
z = w_1x_1 + w_2x_2 + b
\]
\[
\text{output} =
\begin{cases}
1, & z \ge 0 \\
0, & z < 0
\end{cases}
\]

---

### Learning Rule
Weights and bias are updated only when the prediction is wrong:

\[
w = w + \eta \cdot error \cdot x
\]
\[
b = b + \eta \cdot error
\]

Where:
- `error = actual - predicted`
- `η` is the learning rate

---

### Observations
- Initially, the model predicts incorrectly for input `[0, 0]` due to positive bias
- Bias is gradually reduced to shift the decision boundary
- After a few epochs, all predictions become correct
- Once predictions are correct, weights and bias stop changing

Final learned values (approx):
- Weights ≈ `[0.118, 0.722]`
- Bias ≈ `-0.081`

---

### Key Learnings
- A perceptron learns by correcting mistakes
- Bias controls the position of the decision boundary
- Learning stops automatically when no errors remain
- Perceptron can solve **linearly separable problems** like OR
- Perceptron **cannot solve non-linear problems** like XOR

---

### Conclusion
This experiment demonstrates how a single neuron learns a simple logical function using basic update rules. The perceptron forms the foundation of neural networks and helps bridge the gap between classical machine learning and deep learning.

---

### Next Step
Extend this idea to **multi-layer neural networks** to solve non-linear problems such as XOR.
