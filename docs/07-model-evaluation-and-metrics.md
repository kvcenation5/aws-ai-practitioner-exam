# Model Evaluation and Metrics

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Evaluating an AI model correctly is critical for ensuring it is reliable, safe, and cost-effective. The metrics we use depend on whether we are looking at traditional ML (Classification/Regression) or Generative AI (Language/Images).

---

## 🏗️ Model Evaluation Datasets

Evaluation occurs after a model is trained. To ensure a model generalizes well to new data (rather than just memorizing the training data), the available data is typically partitioned into three parts.

![Evaluation Datasets Split](assets/evaluation-datasets.png)

1.  **Training Set (80%)**
    The data used to actually train the model. The model learns patterns and relationships from this set.
2.  **Validation Set (10%)**
    The data set aside to evaluate how the model responds in a non-training environment. You use this data to **improve the model** (tuning hyperparameters) and ensure it generalizes to unseen data.
3.  **Test Set (10%)**
    After you have improved the model using the validation data, you use the test set for a final evaluation. This measures the final predictive quality and ensures the model meets your performance standards before production deployment.

---

## ⚖️ Model Fit

Model fit is essential for understanding the root cause of poor model accuracy. By analyzing where the model fails, you can take specific corrective steps. 

### Detecting Fit via Prediction Error
You can determine the state of your model by comparing the **prediction error** on the **training data** versus the **evaluation data**.

#### 1. Underfitting (High Bias)
*   **Behavior:** Performs poorly on the **training data**.
*   **Cause:** The model is too simple (the input features are not expressive enough).

#### 2. Overfitting (High Variance)
*   **Behavior:** Performs well on **training data** but poorly on **evaluation data**.
*   **Cause:** The model has "memorized" the training noise rather than learning general patterns.

#### 3. Balanced (Ideal)
*   **Goal:** Low bias and low variance. Consistency across both training and evaluation data.

---

## 📊 Classification Problem Metrics

Classification involves Assigning labels or categories to data. Evaluation is done by comparing model predictions against known target values in a "held-out" dataset.

### 🧩 The Confusion Matrix
A confusion matrix is the building block for classification evaluation. It compares **Predicted Classes** against **Actual Classes**.

| | Actual Positive | Actual Negative |
| :--- | :--- | :--- |
| **Predicted Positive** | **True Positive (TP)** | False Positive (FP) |
| **Predicted Negative** | False Negative (FN) | **True Negative (TN)** |

### Key Metrics
*   **Accuracy** 
    *   **Formula:** `(TP + TN) / (TP + TN + FP + FN)`
    *   **Logic:** Overall correctness.
    *   **Limitation:** Less effective when there are many True Negative cases (imbalanced data).
*   **Precision**
    *   **Formula:** `TP / (TP + FP)`
    *   **Focus:** Proportion of positive predictions that are actually correct.
    *   **When to use:** When the cost of **False Positives** is high.
    *   *Example:* **Email Spam Filtering**. You don't want legitimate emails sent to spam.
*   **Recall (Sensitivity)**
    *   **Formula:** `TP / (TP + FN)`
    *   **Focus:** Proportion of actual positives correctly identified.
    *   **When to use:** When the cost of **False Negatives** is high.
    *   *Example:* **Terminal Illness Diagnosis**. It is vital not to miss a sick patient.
*   **F1-Score**
    *   **Logic:** The harmonic mean of Precision and Recall. Best "all-around" metric for imbalanced datasets.
*   **AUC-ROC (Area Under Curve)**
    *   **ROC:** A probability curve plotting True Positive Rate vs. False Positive Rate at various thresholds.
    *   **AUC:** Represents the degree of **separability**. It shows how well the model can distinguish between classes.

---

## 🔢 Regression Problem Metrics

Regression predicts continuous numerical values. Evaluation focuses on the difference between the prediction and the actual outcome.

*   **Mean Squared Error (MSE)**
    *   **Calculation:** Sum up the squares of the differences between predicted and actual values.
    *   **Goal:** The **smaller the MSE**, the better the predictive accuracy.
*   **R-Squared (R²)**
    *   **Logic:** Explains the fraction of variance accounted for by the model (scored 0 to 1).
    *   **Goal:** A value close to 1 indicates the model explains most of the data's variance.

---

## 🧠 Generative AI Metrics (LLMs)

*   **Perplexity (PPL):** Measures "How confused is the model?" **Lower is better.**
*   **ROUGE:** Used for **Summarization**. Focuses on Recall.
*   **BLEU:** Used for **Translation**. Focuses on Precision.

---

## 💼 Business Metrics and KPIs

Model performance must align with business goals established in the **Business Goal Identification** phase.

*   **KPI Alignment:** Link numerical metrics (Precision/Recall) to business results like increasing sales or cutting costs.
*   **Cost Functions:** Specify the economic impact of correct predictions vs. errors.
*   **A/B Testing & Canary Deployments:** Experiment with multiple variants of a model to determine which best achieves business goals in production.

---
*Last Updated: Jan 2026*
