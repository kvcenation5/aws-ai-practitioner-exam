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

!!! tip "Exam Tip: Unstructured Data"
    Generative AI and Foundation Models are primarily used to extract value from **unstructured data** (text, images, video) which traditional ML struggles with.


---

## 2. The Machine Learning Process & Paradigms

Training data is fed into machine learning algorithms to create a model. This process is divided into four broad categories:

### 2.1 Supervised Learning
The algorithms are trained on **labeled data**. 
*   **Goal:** Learn a **mapping function** that can predict the output for new, unseen input data.
*   **Classification:** Assigns labels or categories to data.
    *   **Use Cases:** Fraud detection, Image classification, Customer retention, Diagnostics.
*   **Regression:** Predicts continuous or numerical values.
    *   **Use Cases:** Weather forecasting, Market forecasting, Estimating life expectancy, Advertising popularity.

### 2.2 Unsupervised Learning
Algorithms that learn from **unlabeled data**. 
*   **Goal:** Discover **inherent patterns, structures, or relationships** within the input data.
*   **Clustering:** Groups data based on similar features (e.g., grouping customers by habits).
    *   **Use Cases:** Customer segmentation, Targeted marketing, Recommendation systems.
*   **Dimensionality Reduction:** Reduces the number of features while preserving important patterns.
    *   **Use Cases:** Big data visualization, Meaningful compression, Structure discovery.

### 2.3 Reinforcement Learning
The machine is given only a **performance score** as guidance. An **agent** learns through trial and error as it interacts in an **environment** based on feedback in the form of **rewards and penalties**.
*   **Goal:** Improve decision-making over time to maximize the reward.
*   **Example:** In **AWS DeepRacer**, a virtual car (agent) learns to navigate a track (environment) by receiving rewards for staying on the track and completing it quickly.
*   **Best For:** When the desired outcome is known but the specific path to achieve it requires exploration.

### 2.4 Semi-Supervised Learning
A hybrid approach using a small amount of labeled data and a large amount of unlabeled data to improve accuracy and structure.

!!! note "Exam Perspective: Self-Supervised Learning"
    **Foundation Models** often use **Self-Supervised Learning**, where the data itself provides the labels (e.g., predicting the next word in a sentence).

---

## 3. Determining the Appropriate Solution

Before applying AI or ML, you must determine if it is the right fit for the business problem.

### When AI/ML IS Appropriate:
*   **Manual Rules are Challenging:** When the rules are too complex for humans to code (e.g., Spam filtering with millions of overlapping variables).
*   **Scale is Challenging:** When the volume of data is too large for manual human analysis (e.g., scanning millions of emails in real-time).

### When AI/ML IS NOT Appropriate:
*   **Simple Rules Suffice:** If you can determine the target value using simple math, logic, or predefined steps (e.g., calculating sales tax).
*   **No Data Patterns:** If there is no historical data or patterns to learn from.

---

## 4. Inferencing: Using the Model

Once a model has been trained, it is used to make predictions or decisions on new data. This process is called **Inferencing**. 

There are two main ways to perform inferencing on AWS:

| Type | Description | Use Case |
| :--- | :--- | :--- |
| **Batch Inferencing** | Running predictions on a large group (batch) of data all at once. Usually processed on a schedule (e.g., overnight). | Monthly credit scores, product recommendation emails, financial reporting. |
| **Real-time Inferencing** | Running predictions immediately as new data arrives. Requires low-latency response. | Fraud detection at checkout, chatbot responses, navigation apps. |

!!! tip "Exam Tip: Cost vs. Performance"
    **Batch Inferencing** is generally more cost-effective because it doesn't require "always-on" infrastructure, while **Real-time Inferencing** is required for interactive user experiences.


---

---

## 5. Model Performance Concepts


*   **Underfitting (High Bias):** The model is too simple. Performs poorly on both training and test data.
*   **Overfitting (High Variance):** The model "memorizes" the training data. Performs great on training data but fails on new data.
*   **The 70/15/15 Split:** A common practice to split data into **Training** (70%), **Validation** (15% for tuning), and **Test** (15% for final evaluation).

!!! warning "Exam Perspective: Fixing Overfitting"
    To fix **overfitting**, you can:
    1.  Provide more training data.
    2.  Simplify the model (reduce features).
    3.  Use **Regularization** techniques.


---

---

## 6. Evaluation Metrics


*   **Accuracy:** Percentage of correct predictions.
*   **Precision:** How many of the "Positive" predictions were actually correct? (**Avoids False Positives**).
*   **Recall:** How many of the actual "Positives" did we find? (**Avoids False Negatives**).
*   **F1-Score:** The balance between Precision and Recall.
*   **RMSE:** Root Mean Square Error, used to measure accuracy in **Regression** problems.

!!! info "Exam Perspective: Precision vs. Recall"
    *   Use **Precision** when the cost of a False Positive is high (e.g., marking a legitimate email as Spam).
    *   Use **Recall** when the cost of a False Negative is high (e.g., missing a Cancer diagnosis).
    *   **F1-Score** is the best "all-around" metric when you have an imbalanced dataset.


---
*Last Updated: Jan 2026*
