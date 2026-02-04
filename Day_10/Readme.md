DAY 10 – LEARNING RATE COMPARISON AND OPTIMIZATION BEHAVIOR

Objective
---------
The objective of this experiment is to understand how the learning rate affects
training behavior, convergence speed, and final loss during optimization.

The experiment focuses on logistic regression trained using gradient descent
on a real dataset with properly scaled features.

--------------------------------------------------

Experiment Setup
----------------
- Model: Logistic Regression (implemented from scratch)
- Dataset: Breast Cancer Wisconsin Dataset
- Feature Scaling: StandardScaler (mean = 0, std = 1)
- Optimization: Gradient Descent
- Loss Function: Binary Cross-Entropy
- Epochs: Fixed number for all experiments

Different learning rates were tested while keeping all other factors constant.

--------------------------------------------------

Learning Rate Results
---------------------
Learning Rate: 0.0001
Final Loss: 0.5469

Learning Rate: 0.01
Final Loss: 0.1071

Learning Rate: 0.1
Final Loss: 0.0613

Learning Rate: 1.0
Final Loss: 0.0432

--------------------------------------------------

Observations
------------
1. Very small learning rate (0.0001):
   - Loss decreases very slowly
   - Training is stable but inefficient
   - Model under-trains within the fixed number of epochs

2. Moderate learning rates (0.01 and 0.1):
   - Loss decreases smoothly and efficiently
   - Faster convergence
   - Stable optimization behavior

3. Large learning rate (1.0):
   - Achieves the lowest final loss in this setup
   - Works because:
     - Logistic regression loss is convex
     - Features are properly scaled
   - Converges faster, but is aggressive

--------------------------------------------------

Important Notes
---------------
- A higher learning rate does not always mean better performance.
- The success of a large learning rate here depends on:
  - Convex loss function
  - Feature normalization
  - Fixed training duration

- In other models or with more epochs, a learning rate of 1.0 may:
  - Oscillate
  - Become unstable
  - Diverge

--------------------------------------------------

Key Takeaways
-------------
- Learning rate controls the step size of gradient descent.
- Too small learning rates lead to slow convergence.
- Too large learning rates can cause instability.
- Proper feature scaling allows the use of larger learning rates safely.
- Learning rate selection is data-dependent and model-dependent.

--------------------------------------------------

Conclusion
----------
This experiment demonstrates that learning rate is a critical hyperparameter.
Even with correct gradients and a good model, an inappropriate learning rate
can prevent successful training.

A well-chosen learning rate enables fast and stable convergence, while poor
choices lead to slow learning or divergence.

--------------------------------------------------

Next Step
---------
Study advanced optimization techniques such as Momentum, RMSProp, and Adam,
which adapt learning rates automatically during training.
