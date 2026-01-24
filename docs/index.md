# Machine Learning Fundamentals

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Building a machine learning model involves a systematic process: collecting and preparing data, selecting an appropriate algorithm, training the model on the prepared data, and evaluating its performance through testing and iteration.

---

## 1. The Foundation: Training Data

The machine learning process starts with collecting and processing **training data**. An ML model is only as good as the data used to train it.

!!! failure "Garbage In, Garbage Out (GIGO)"
    Bad data leads to bad models. Although data preparation is often a routine process, it is the most critical stage. It can make the model work as intended or completely ruin its performance.

### Data Types: Labeled vs. Unlabeled
*   **Labeled Data:** Data that already contains the "answer" or the target attribute you want the model to predict (e.g., an image of a cat marked as "Cat").
*   **Unlabeled Data:** Information that has no predefined labels or categories. The model must find its own patterns.

### Structured vs. Unstructured Data
| Data Category | Characteristics | Examples |
| :--- | :--- | :--- |
| **Structured** | Highly organized, formatted in rows/columns. Easily searchable. | Excel sheets, SQL databases, CSV files. |
| **Unstructured** | No predefined format. Difficult to collect and analyze. | Images, audio files, videos, PDF documents, social media posts. |

---

## 2. The Machine Learning Process & Paradigms

Training data is fed into machine learning algorithms to create a model. This process is divided into four broad categories:

### Supervised Learning
The model is trained on **labeled data**. 
*   **Goal:** Learn a "mapping function" to predict output for new, unseen data based on known examples.
*   **Types:** Classification (Categories) and Regression (Numbers).

### Unsupervised Learning
The model learns from **unlabeled data**.
*   **Goal:** Discover inherent patterns, structures, or hidden relationships within the data.
*   **Examples:** Clustering (grouping customers) and Association.

### Reinforcement Learning
The model learns through trial and error in an environment.
*   **Goal:** Improve decision-making over time to maximize a reward.
*   **Mechanics:** Uses a system of **rewards and penalties**.

### Semi-Supervised Learning
A hybrid approach where only a **small portion** of the training data is labeled. The model uses the labeled data to understand the structure and the unlabeled data to generalize and improve accuracy.

---

## 3. Inferencing: Using the Model

Once a model has been trained, it is used to make predictions or decisions on new data. This process is called **Inferencing**. 

There are two main ways to perform inferencing on AWS:

| Type | Description | Use Case |
| :--- | :--- | :--- |
| **Batch Inferencing** | Running predictions on a large group (batch) of data all at once. Usually processed on a schedule (e.g., overnight). | Monthly credit scores, product recommendation emails, financial reporting. |
| **Real-time Inferencing** | Running predictions immediately as new data arrives. Requires low-latency response. | Fraud detection at checkout, chatbot responses, navigation apps. |

---

## 4. Model Performance Concepts

*   **Underfitting (High Bias):** The model is too simple to capture the underlying patterns. Performs poorly on both training and test data.
*   **Overfitting (High Variance):** The model "memorizes" the training data including the noise. Performs great on training data but fails on new, unseen data.
*   **The 70/15/15 Split:** A common practice to split data into **Training** (70%), **Validation** (15% for tuning), and **Test** (15% for final evaluation).

---

## 5. Evaluation Metrics

*   **Accuracy:** Percentage of correct predictions.
*   **Precision:** How many of the "Positive" predictions were actually correct? (Avoids False Positives).
*   **Recall:** How many of the actual "Positives" did we find? (Avoids False Negatives).
*   **F1-Score:** The balance between Precision and Recall.
*   **RMSE:** Root Mean Square Error, used to measure accuracy in **Regression** problems.

---
*Last Updated: Jan 2026*
