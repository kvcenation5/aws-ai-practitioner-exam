# Machine Learning Fundamentals

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

## 1. Core Concepts
*   **Machine Learning (ML):** Teaching computers to learn from data without explicit programming.
*   **Traditional vs ML:** Traditional uses rules + data -> output. ML uses data + answers -> rules (model).

## 2. Types of Machine Learning
| Type | Data Used | Goal | Example |
| :--- | :--- | :--- | :--- |
| **Supervised** | Labeled | Predict labels | Spam detection, Price prediction |
| **Unsupervised** | Unlabeled | Find patterns | Customer segmentation |
| **Reinforcement** | Rewards/Penalties | Optimize actions | Game AI, Robotics |

### Supervised Learning Sub-types
*   **Classification:** Discrete categories (Binary: Yes/No; Multi-class: Cat/Dog/Bird).
*   **Regression:** Continuous values (e.g., house prices, temperature).

### Unsupervised Learning Sub-types
*   **Clustering:** Grouping similar items (K-Means).
*   **Dimensionality Reduction:** Simplifying data (PCA).

## 3. Key Vocabulary
*   **Features:** Input variables (e.g., sq footage, # of rooms).
*   **Labels:** Target variable (e.g., house price).
*   **Model:** The mathematical representation learned from data.
*   **Inference:** Using a trained model to make predictions on new data.

## 4. The ML Pipeline
1.  **Problem Definition:** What are we solving?
2.  **Data Collection:** Gathering raw data (S3, RDS).
3.  **Data Prep/Feature Engineering:** Cleaning, scaling, selecting features.
4.  **Model Training:** Feeding data to algorithms (SageMaker).
5.  **Evaluation:** Checking accuracy on test data.
6.  **Tuning:** Adjusting hyperparameters.
7.  **Deployment:** Hosting the model for use (SageMaker Endpoints).
8.  **Monitoring:** Tracking performance over time (Model Monitor).

## 5. Model Performance Issues
*   **Underfitting (High Bias):** Model is too simple; performs poorly on both training and test data.
*   **Overfitting (High Variance):** Model is too complex; performs great on training data but poorly on unseen test data.
*   **Data Split:** Usually 70% Training / 15% Validation / 15% Test.

## 6. Evaluation Metrics
*   **Accuracy:** Overall correctness.
*   **Precision:** TP / (TP + FP) -> Avoid "False Alarms".
*   **Recall:** TP / (TP + FN) -> Avoid "Misses".
*   **F1-Score:** Harmonic mean of Precision and Recall.
*   **RMSE:** Common for regression; measures error magnitude.

## 7. AWS AI/ML Service Stack
*   **AI Services:** Pre-built (Rekognition, Comprehend, Lex, Polly, Transcribe).
*   **ML Services:** Managed platform (Amazon SageMaker).
*   **Infrastructure:** P-series instances (GPUs), Trainium, Inferentia.

---
*Last Updated: Jan 2026*
