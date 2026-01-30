## Day 7 – Backpropagation (Conceptual Understanding)

### Goal
Understand how backpropagation works and how weights and bias are updated using gradients.

---

### What is Backpropagation?
Backpropagation is the process of sending the error from the output back to the model parameters in order to update them and reduce the loss.

It tells the model:
- what went wrong
- where it went wrong
- how much each parameter contributed to the error

---

### Model Used (Conceptually)
A simple linear model:

y = wx + b

- `w` controls the slope of the line  
- `b` controls the vertical shift  

---

### Loss Function
Squared Error Loss:

L = (y_pred − y)²

This measures how far the prediction is from the actual value.

---

### Key Gradients

Gradient of loss with respect to prediction:

dL/dy_pred = 2(y_pred − y)

---

Gradient with respect to weight:

dL/dw = 2(y_pred − y) · x

---

Gradient with respect to bias:

dL/db = 2(y_pred − y)

---

### Parameter Update Rule
Using gradient descent:

w = w − α · dL/dw  
b = b − α · dL/db  

Where α is the learning rate.

---

### What Actually Happens During Learning
- The model makes a prediction
- The error is calculated
- Gradients show how parameters caused the error
- Weight updates change the slope
- Bias updates shift predictions up or down
- Loss decreases over time

---

### Important Intuition
- Weight learns the relationship between input and output
- Bias learns the baseline offset
- Both are updated together
- Learning stops when gradients become very small

---

### Key Takeaways
- Backpropagation is just the chain rule applied repeatedly
- Gradients flow backward from loss to parameters
- Correct gradient computation is essential for learning
- This same logic scales to deep neural networks

---

### Next Step
Apply this understanding to multi-layer networks and study how gradients flow through hidden layers and activation functions.
