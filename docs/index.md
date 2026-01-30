# Machine Learning Fundamentals

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Building a machine learning model involves a systematic process: collecting and preparing data, selecting an appropriate algorithm, training the model on the prepared data, and evaluating its performance through testing and iteration.

---

## 1. The Foundation: Training Data

### 1. The Foundation: Training Data

The machine learning process starts with collecting and processing **training data**. 

*   **What is Training Data?** It is a "Teacher's Guide" containing thousands of examples (Inputs) and their correct answers (Labels).
*   **The Training Process:** The model doesn't just look at the data once. It looks at it through many repetitions (**Epochs**). In each epoch, the model makes a guess, checks the answer, and adjusts its internal math to get closer to the truth.

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

### 1.1 Quick Rule of Thumb: Supervised vs. Unsupervised

| Learning Type | Keyword | Analogy | Exam Trigger Words |
| :--- | :--- | :--- | :--- |
| **Supervised** | **Answers** | A student with an answer key. | "Labeled data", "Predict $X$", "Classify as $Y$". |
| **Unsupervised**| **Patterns** | An explorer discovering a new land. | "Unlabeled", "Groups", "Clusters", "Anomalies". |

!!! warning "Common Misconception: Prediction vs. Discovery"
    It is a common mistake to think Unsupervised is for prediction. Remember:

    #### 1. Supervised Learning = Prediction 🎯
    You give the model "Factual Data" (Labeled examples) so that it can **Predict** those same facts for new data.
    *   **The Fact:** "This transaction was Fraud."
    *   **The Prediction:** "Based on the facts I learned, I **predict** this new transaction is also Fraud."
    *   **Exam Logic:** If the goal is to **Predict** a specific value (Price, Category, Yes/No), it is **Supervised**.

    #### 2. Unsupervised Learning = Discovery 🔍
    Since you don't have "Facts" (Labels), you aren't predicting a right answer. Instead, you are **Discovering** hidden structures.
    *   **The Discovery:** "I noticed these 5,000 customers all buy diapers and beer at 7 PM on Fridays."
    *   **The Value:** You didn't "predict" they would do that; you **discovered** a group you didn't know existed.
    *   **Exam Logic:** If the goal is to **Discover** groups, patterns, or anomalies, it is **Unsupervised**.


---

## 2. The Machine Learning Paradigms
Training data is fed into machine learning algorithms to create a model. This process is divided into four broad categories:

### 2.1 Supervised Learning
The algorithms are trained on **labeled data**. 
*   **Goal:** Learn a **mapping function** that can predict the output for new, unseen input data.

!!! info "What is a Mapping Function?"
    Think of it as a mathematical "rule" or "recipe" ($Y=f(X)$). The model analyzes labeled examples to figure out the specific rule that transforms **Inputs (X)** into **Outputs (Y)**. Once it knows the rule, it can apply it to brand-new data to make a prediction.
*   **Classification:** Assigns labels or categories to data.
    *   **Use Cases:** Fraud detection, Image classification, Customer retention, Diagnostics.
*   **Regression:** Predicts continuous or numerical values.
    *   **Use Cases:** Weather forecasting, Market forecasting, Estimating life expectancy, Advertising popularity.

!!! tip "How to Choose: Classification vs. Regression?"
    In the exam, look at the **target value** the algorithm is trying to predict:
    *   **Discrete (Categories):** If the answer is a "Word" or a specific "Group" (e.g., Cat vs. Dog), use **Classification**.
    *   **Continuous (Numbers):** If the answer is a "Measurement" or a "Count" (e.g., $450.25 or 72 degrees), use **Regression**.

### 2.2 Unsupervised Learning
Algorithms that learn from **unlabeled data**. 
*   **Goal:** Discover **inherent patterns, structures, or relationships** within the input data.

#### How it Works:
*   **Clustering:** Groups data based on **Similarity** and **Distance**. Even without labels, the model identifies which items "look alike" and puts them in groups.
    *   **Use Cases:** Customer segmentation, Targeted marketing, Recommendation systems.
*   **Dimensionality Reduction:** Simplifies large datasets by removing **Noise** and **Redundant** features. 
    - **Mechanism:** It squishes 100s of variables into 2 or 3 "main" dimensions to help with **Visualization** and speed.
    - **ELI5 Analogy:** Imagine you have a LEGO piece with 20 different details (color, weight, factory, material). Dimensionality reduction is like picking only the 2 or 3 most important details (size and color) so you can describe the piece simply without getting overwhelmed by the boring stuff.
    - **Use Cases:** Big data visualization, Significant compression, Structure discovery.

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

## 5. Model Performance Concepts (Bias & Variance)

Accuracy is the #1 problem in AI applications. If a model is not trained properly, it will produce inaccurate results. This is measured through two primary metrics: **Bias** and **Variance**.

### 5.1 Bias (Underfitting)
*   **Definition:** Bias measures the difference between the model's expected predictions and the true values. 
*   **High Bias:** The model is too simple and misses important features of the dataset.
*   **ELI5 Analogy:** You tell a kid a dog is just "a thing with 4 legs." The kid sees a cow and calls it a dog because they were too simple.
*   **Result (Underfitting):** The model performs poorly on **both** the training data and new data.

### 5.2 Variance (Overfitting)
*   **Definition:** Variance refers to the model's sensitivity to "noise" or fluctuations in the training data.
*   **High Variance:** The model becomes too familiar with the training data and "memorizes" it instead of learning general patterns.
*   **ELI5 Analogy:** You show a kid your tiny white poodle. The kid memorizes it so perfectly that when they see a big brown dog, they say "That's not a dog!" because it's not exactly like the one they saw.
*   **Result (Overfitting):** The model performs with high accuracy on training data but **fails significantly** when introduced to new, unseen data.

### 5.3 The Bias-Variance Tradeoff
The goal is to find the perfect balance:
*   **Balanced Model:** Low bias and low variance. It captures enough patterns without memorizing the noise.
*   **The Tradeoff:** Decreasing bias often increases variance, and vice versa. ML engineers aim for the "sweet spot" that minimizes both.

### 5.4 Techniques to Overcome Errors
| Technique | Goal | How it Works |
| :--- | :--- | :--- |
| **Cross-Validation** | Detect Overfitting | Training the model on different subsets of data to evaluate consistency. |
| **Increase Data** | Reduce Variance | Adding more samples increases the model's learning scope. |
| **Regularization** | Prevent Overfitting | Penalizes extreme weight values in linear models. |
| **Simpler Models** | Fix Overfitting | Reducing complexity prevents the model from memorizing noise. |
| **Dimension Reduction** | Simplify Data | (e.g., PCA) Reduces features while retaining essential info. |
| **Stop Early** | Prevent Overfitting | Ending training before the model starts "memorizing" the data. |

!!! note "Infra vs. Logic"
    For the exam, remember: **Bias and Variance are "Logic" problems.**
    *   **Underfitting** isn't caused by a slow CPU; it's caused by a **math formula** that is too simple.
    *   **Overfitting** isn't caused by too much RAM; it's caused by a **math formula** that is too complex and "memorizes" the noise.
    *   **AWS Infrastructure** (like SageMaker GPU instances) just determines how *fast* or *large* of a model you can train.

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
