Notes – Supervised Machine Learning (Part 9): Bias–Variance Trade-off

1. Overview

This section explains how model complexity, bias, and variance interact to determine model performance.

Goal: find the optimal balance between bias, variance, and total error to avoid both underfitting and overfitting.

2. Model Complexity vs. Error
 <img width="890" height="497" alt="image" src="https://github.com/user-attachments/assets/2a900ec7-3737-48ea-b7ff-0081cb63e823" />

Too simple (left side) → both training and test errors are high → underfitting.

Too complex (right side) → training error low but test error high → overfitting.

Middle (sweet spot) → both training and test errors are relatively low → best generalization.

As complexity increases, training error decreases continuously, but test error follows a U-shaped curve.
<img width="1079" height="574" alt="image" src="https://github.com/user-attachments/assets/678fd249-01f2-4947-870a-1cdeca1099db" />


3. Definitions

Bias:

The model’s tendency to miss the true relationship between X and Y.

High bias → model is too simple or missing key patterns.

Associated with underfitting.

Example behavior: consistent but wrong predictions (systematic error).

Variance:

The model’s sensitivity to small fluctuations in the training data.

High variance → model overreacts to noise.

Associated with overfitting.

Example behavior: predictions change drastically with small data changes.

4. Visualization (Conceptually)
<img width="1068" height="591" alt="image" src="https://github.com/user-attachments/assets/85ea7853-5e1f-407c-b401-fd1da74824db" />


High Bias, Low Variance: consistent but far from target → misses systematically.

Low Bias, High Variance: sometimes hits target but scattered → unstable predictions.

High Bias, High Variance: worst case → wrong and inconsistent.

Low Bias, Low Variance: ideal case → accurate and consistent predictions.

5. Sources of Model Error
<img width="988" height="615" alt="image" src="https://github.com/user-attachments/assets/3a28aa5e-b4a2-4b81-b9d0-8c55f8a872b9" />


Bias Error – due to wrong model assumptions or missing patterns.

Variance Error – due to excessive model complexity fitting noise.

Irreducible Error – randomness inherent in real-world data; cannot be removed.

Total error = Bias² + Variance + Irreducible error.

<img width="871" height="575" alt="image" src="https://github.com/user-attachments/assets/9f35b202-9422-4658-8f92-c25dd32ad603" />


6. Relationship Between Bias, Variance, and Complexity

As model complexity increases:

Bias decreases (better fit to training data).

Variance increases (less stable, more sensitive to noise).

As model complexity decreases:

Bias increases (misses real patterns).

Variance decreases (more stable but less accurate).

The bias–variance trade-off lies in finding the point of minimum combined error.

7. Key Takeaways

Notes – Supervised Machine Learning (Part 10): Regularization & Model Selection

1. Overview

Goal: use regularization to control model complexity and balance bias and variance.

Regularization helps prevent overfitting — when a model fits the training data too closely but fails to generalize.

This section introduces Ridge, Lasso, Elastic Net, and Recursive Feature Elimination (RFE) as tools for managing complexity and selecting important features.

2. Recap: Complexity vs. Error

Increasing complexity → training error ↓, test error ↑ (overfitting).

Simpler model → higher bias, lower variance (underfitting).

Regularization provides a way to fine-tune complexity without discarding the entire model.

Underfitting → high bias, low variance → overly simplistic model.

Overfitting → low bias, high variance → overly complex model.

The goal is to locate the balance point where total error (bias² + variance) is minimal.

Perfect accuracy is impossible due to irreducible noise in real-world data; good modeling accepts small error for better generalization.


What is Regularization
<img width="1027" height="462" alt="Screenshot 2025-10-04 234926" src="https://github.com/user-attachments/assets/348e6104-57c9-43d1-968a-0ed9666be438" />


In standard training, we minimize a cost function such as Mean Squared Error (MSE):
λ (lambda): regularization strength.

R(w): penalty function based on parameter size.

Larger λ → stronger penalty → simpler model (higher bias, lower variance).

Smaller λ → weaker penalty → more complex model (lower bias, higher variance).

4. Intuition

Regularization discourages large coefficients → limits how much each feature can influence predictions.

This reduces model variance and improves generalization to unseen data.

It acts as an automatic complexity control.
