## Day 3 – Loss Function & Gradient Descent (From Scratch)

### Objective
To understand how machine learning models learn by minimizing a loss function using Gradient Descent, and to implement this process from scratch using NumPy.

---

### Problem Setup
- Simple linear regression problem  
- Model:  
  \[
  \hat{y} = wx + b
  \]
- True relationship in data:  
  \[
  y = 2x
  \]

---

### Loss Function
**Mean Squared Error (MSE)** is used:

\[
L = \frac{1}{n}\sum (y - \hat{y})^2
\]

Why MSE:
- Prevents positive and negative errors from cancelling
- Penalizes larger errors more
- Smooth and differentiable (good for optimization)

---

### Gradient Descent
Parameters are updated iteratively using gradients:

\[
\frac{\partial L}{\partial w} = -2 \cdot \text{mean}(x(y - \hat{y}))
\]

\[
\frac{\partial L}{\partial b} = -2 \cdot \text{mean}(y - \hat{y})
\]

Update rule:
\[
w = w - \alpha \cdot \frac{\partial L}{\partial w}
\]
\[
b = b - \alpha \cdot \frac{\partial L}{\partial b}
\]

---

### Observations
- Loss decreases rapidly in early epochs and slowly later
- Weight `w` gradually approaches the true value (~2)
- Bias `b` adjusts to correct baseline offset
- Gradient descent converges smoothly toward minimum loss

Sample result:
- Initial loss ≈ 41.6  
- Final loss ≈ 0.83  
- Learned parameters:  
  - `w ≈ 1.86`  
  - `b ≈ 0.22`

---

### Key Learnings
- Models do not learn accuracy; they minimize loss
- Gradient descent follows the slope of the loss function
- Learning rate controls step size and convergence
- Bias allows the model to shift predictions vertically
- This mechanism is the foundation of all ML and DL training

---

### Conclusion
This experiment provides a clear, intuitive understanding of how learning happens in machine learning models. Loss functions and gradient descent together form the backbone of algorithms ranging from linear regression to deep neural networks.

---

### Next Step
Explore **activation functions** to understand why non-linearity is essential in neural networks.
