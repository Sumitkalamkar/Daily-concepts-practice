## Week 1 – Day 1: Data Understanding & Feature Scaling

### Dataset
Breast Cancer Wisconsin Dataset (sklearn)

Binary classification problem with 30 numerical features.

---

### Objective
To understand the dataset and analyze the effect of feature scaling before training any machine learning model.

---

### Steps Performed

1. Loaded the dataset and inspected feature distributions
2. Analyzed basic statistics (mean, std, min, max)
3. Split data into training and testing sets
4. Applied StandardScaler to normalize features
5. Compared statistics before and after scaling

---

### Observations (Before Scaling)

From the descriptive statistics:

- Different features had very different ranges  
  - `mean smoothness` ranged around **0.05 – 0.16**
  - `mean radius` ranged around **7 – 28**
  - `mean area` ranged around **143 – 2501**

This indicates that features are measured in different units and scales.

---

### Observations (After Scaling)

After applying StandardScaler:

- Mean of each feature ≈ **0**
- Standard deviation of each feature ≈ **1**
- Feature values are centered and comparable across dimensions

Example:
- `mean radius` and `area error` both follow a normalized distribution after scaling

---

### Key Learning

- Feature scaling does **not change the underlying data relationships**
- It only standardizes the units of measurement
- Gradient-based models (Logistic Regression, Neural Networks) perform better when features are on similar scales
- Scaling helps in faster convergence and stable optimization

---

### Why This Step Is Important

Without scaling:
- Large-valued features dominate gradients
- Model training becomes unstable or biased

With scaling:
- All features contribute fairly
- Optimization becomes smoother and more reliable

---

### Conclusion

This step builds a strong foundation for training machine learning models.  
The preprocessed data is now ready for Logistic Regression and Neural Networks, which will be explored next.

---

### Next Step
Train Logistic Regression and compare model performance **with and without feature scaling**.
