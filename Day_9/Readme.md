# Day 9 – Regularization on a Real Dataset (Logistic Regression)

This experiment demonstrates the effect of regularization on model generalization using a real-world dataset and Logistic Regression.

The goal is to understand how regularization affects training accuracy, testing accuracy, and overfitting behavior.

---

## Dataset Used

The Breast Cancer Wisconsin dataset was used for this experiment.  
It is a real medical dataset with:
- Multiple numerical features
- Binary classification target
- Moderate dataset size, making it suitable for studying overfitting

The dataset was split into training and testing sets, and features were standardized before training.

---

## Models Compared

Two Logistic Regression models were trained:

1. Logistic Regression without regularization  
2. Logistic Regression with L2 regularization (weight decay)

Both models were trained using the same data split and preprocessing to ensure a fair comparison.

---

## Results

### No Regularization

- Training Accuracy: 0.9912  
- Testing Accuracy: 0.9561  

The model fits the training data very well, achieving almost perfect training accuracy.  
However, the gap between training and testing accuracy indicates overfitting.  
The model relies on larger weights and becomes more sensitive to training data patterns.

---

### L2 Regularization

- Training Accuracy: 0.9868  
- Testing Accuracy: 0.9737  

With L2 regularization, training accuracy decreases slightly.  
However, testing accuracy improves noticeably compared to the non-regularized model.

This shows that regularization reduces overfitting and improves generalization.

---

## Interpretation

Regularization intentionally penalizes large weights, which:
- reduces model sensitivity
- prevents memorization of training data
- encourages smoother decision boundaries

Although training error increases slightly, testing performance improves.  
This confirms that the goal of regularization is not to minimize training error, but to minimize error on unseen data.

---

## Key Takeaways

- High training accuracy does not guarantee good generalization  
- Regularization reduces the gap between training and testing performance  
- L2 regularization improves stability by discouraging large weights  
- A small increase in training error can lead to a significant decrease in testing error  

---

## Conclusion

This experiment clearly shows why regularization is essential in real-world machine learning.  
By controlling weight magnitude, L2 regularization produces models that generalize better and perform more reliably on unseen data.

---

## Next Step

Explore learning rate behavior and optimization strategies to further improve training stability and convergence.
