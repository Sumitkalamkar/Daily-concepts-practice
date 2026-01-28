## Day 4 – Activation Functions (Sigmoid, Tanh, ReLU)

### Objective
To understand why activation functions are required in neural networks and to visualize the behavior of common activation functions.

---

### Why Activation Functions Are Needed
If a neural network uses only linear operations, stacking multiple layers still results in a linear model.  
Activation functions introduce **non-linearity**, which allows neural networks to learn complex patterns and decision boundaries.

---

### Activation Functions Studied

#### 1. Sigmoid
\[
\sigma(x) = \frac{1}{1 + e^{-x}}
\]

- Output range: (0, 1)
- Often used in binary classification output layers
- Problem: suffers from **vanishing gradient** for large positive or negative inputs

---

#### 2. Tanh
\[
\tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}
\]

- Output range: (-1, 1)
- Zero-centered (better than sigmoid)
- Still suffers from vanishing gradient at extreme values

---

#### 3. ReLU
\[
\text{ReLU}(x) = \max(0, x)
\]

- Output range: [0, ∞)
- Fast and computationally efficient
- Helps mitigate vanishing gradient for positive inputs
- Can produce sparse activations
- Problem: **Dying ReLU** for negative inputs

---

### Visualization
The activation functions were plotted over a range of input values to observe their behavior:

- Sigmoid and Tanh saturate at extreme values
- ReLU grows linearly for positive inputs
- ReLU outputs zero for negative inputs, leading to sparse activation

---

### Key Learnings
- Activation functions enable neural networks to model non-linear relationships
- Sigmoid and Tanh can cause vanishing gradient issues
- ReLU is the most commonly used activation function in hidden layers
- ReLU improves gradient flow but has its own limitations

---

### Conclusion
Activation functions are a fundamental component of neural networks.  
Among the common choices, ReLU is widely preferred for hidden layers due to its simplicity and effectiveness, while Sigmoid and Tanh are mainly used in specific scenarios.

---

### Next Step
Study the **Perceptron and single neuron model** to understand how weights, bias, and activation functions work together.
