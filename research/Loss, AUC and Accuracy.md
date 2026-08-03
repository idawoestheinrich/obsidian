---
tags:
  - type/concept
  - topic/machine_learning
aliases:
  - acccuracy
  - AUC
  - Loss
---
## 🔹 1. **Loss**
- **What it is**: A number that measures how far off your model’s predictions are from the true values.
- It comes from the **loss function** (e.g. cross-entropy for classification, mean squared error for regression).
- **Lower is better**.
- During training, the optimizer tries to minimize this number.
👉 Think of it as the “raw score” the model is trying to improve.
## 🔹 2. **Accuracy**
- **What it is**: The percentage of predictions your model got _exactly right.
- Formula:
```
Accuracy = #correct predictions/total predictions
```
- **Higher is better**.
- Works well when classes are balanced (e.g. 50/50 cats vs dogs).
⚠️ **But accuracy can be misleading**:  
If 95% of your data is “not signal” and only 5% is “signal,” a dumb model that always predicts “not signal” will get 95% accuracy but be useless.
## 🔹 3. **AUC (Area Under the ROC Curve)**
- **What it is**: Measures how well your model separates classes at different thresholds.
- Instead of asking “did it predict exactly right,” it asks:
    - How good is the model at ranking true positives higher than false positives?
- Value range:
    - 0.5 → random guessing
    - 1.0 → perfect separation
- **AUC is more reliable than accuracy** when you have **imbalanced datasets** (common in physics, e.g. rare signals among lots of background).