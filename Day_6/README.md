## Day 6 – Multi-Layer Neural Network Solving XOR (From Scratch)

### Objective
To understand why a single perceptron fails on non-linear problems and how a multi-layer neural network with non-linearity and backpropagation can successfully solve the XOR problem.

---

### Problem: XOR
The XOR function is not linearly separable, meaning it cannot be solved using a single linear decision boundary.

| x1 | x2 | y |
|----|----|---|
| 0  | 0  | 0 |
| 0  | 1  | 1 |
| 1  | 0  | 1 |
| 1  | 1  | 0 |

---

### Model Architecture
A simple feedforward neural network was implemented from scratch:


---

### Why a Hidden Layer is Required
- A single perceptron can only learn linear decision boundaries
- XOR requires different behavior in different regions of the input space
- The hidden layer learns intermediate non-linear features
- Non-linearity enables region-wise decision making

---

### Activation Functions Used
- **tanh** (hidden layer):  
  - Zero-centered  
  - Prevents dead neurons  
  - Enables non-linear feature learning
- **sigmoid** (output layer):  
  - Produces probability-like output for binary classification

---

### Loss Function
Binary Cross-Entropy loss was used:

\[
L = -\left[y\log(\hat{y}) + (1-y)\log(1-\hat{y})\right]
\]

This loss is well-suited for binary classification and works effectively with sigmoid activation.

---

### Training Results
The model was trained using gradient descent and backpropagation.

Loss decreased smoothly over epochs:


Final predictions closely matched the XOR targets.

---

### Key Learnings
- XOR is not linearly separable
- Non-linearity is essential for learning complex patterns
- Hidden layers enable region-wise logic
- Backpropagation propagates error backward using the chain rule
- Proper activation and loss functions are critical for learning

---

### Conclusion
This experiment demonstrates how multi-layer neural networks overcome the limitations of linear models. By combining hidden layers, non-linear activation functions, and backpropagation, the network successfully learns the XOR function from scratch.

---

### Next Step
Deepen understanding of **backpropagation**, gradient flow, and how these concepts scale to deeper neural networks.
