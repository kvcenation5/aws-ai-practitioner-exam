# Hyperparameters Deep Dive

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

In machine learning, there is a big difference between **Parameters** (the model's internal knowledge) and **Hyperparameters** (the external settings we choose).

---

## 🏗️ 1. Parameters vs. Hyperparameters

| Feature | Parameters | Hyperparameters |
| :--- | :--- | :--- |
| **What they are** | Internal variables learned by the model from data. | External configuration settings set by the developer. |
| **When they are set** | Automatically derived **during** training. | Manually set **before** training begins. |
| **Example** | Weights and Biases in a neural network. | Learning Rate, Batch Size, Epochs. |

---

## 🎨 2. Common Hyperparameters (The ML "Knobs")

### 🚀 1. Learning Rate
*   **What it is:** Controls how much the model changes its internal logic in response to the error it finds each time it sees data.
*   **The Goldilocks Problem:**
    *   **Too High:** The model "jumps" over the optimal solution. It trains fast but never gets accurate.
    *   **Too Low:** The model takes tiny baby steps. It is very accurate but takes forever (and costs more in AWS compute bills!).
*   **Analogy:** Adjusting the temperature on a stove. Too high and you burn the food; too low and it never cooks.

### 📦 2. Batch Size
*   **What it is:** The number of training examples processed in one single step.
*   **Tradeoff:**
    *   **Small Batch:** More updates, more accurate learning, but slower.
    *   **Large Batch:** Faster processing, uses more memory (GPU RAM), but can lead to "blurry" learning.

### 🔄 3. Number of Epochs
*   **What it is:** How many times the model sees the entire dataset.
*   **The Overfitting Risk:** If you run too many epochs, the model starts to **memorize** the specific data rather than learning the general pattern.

### 🌳 4. Algorithm-Specific Hyperparameters
*   **kNN:** The value of **$k$** (How many neighbors to look at).
*   **Decision Trees:** **Max Depth** (How many levels the tree can grow).
*   **Deep Learning:** Number of layers and neurons.

---

## 🛠️ 3. How to Find the Best Settings

Since there are millions of possible combinations, we use **Hyperparameter Optimization (HPO)**.

### 1. Grid Search
*   **Logic:** Try every single possible combination of a list you provide. 
*   **Con:** Very slow and expensive.

### 2. Random Search
*   **Logic:** Pick random combinations from a range. 
*   **Pro:** Surprisingly effective and much faster than Grid Search.

### 3. Bayesian Optimization (SageMaker's Secret Sauce)
*   **Logic:** The "Smart Way." It treats the tuning process like its own ML problem. It looks at the results of previous tries to guess which settings will work better in the next run.
*   **AWS Service:** **Amazon SageMaker Automatic Model Tuning (AMT)**.

---

## 🎓 Exam Tips & Tricks

!!! tip "Where do we tune?"
    Hyperparameters are always tuned using the **Validation Dataset**. Once you find the best knobs, you check the final score on the **Test Dataset**.

!!! tip "Budget Tip"
    If the exam asks how to find the best model while **saving time/money**, the answer is often **Random Search** or **SageMaker Automatic Model Tuning** (which uses Bayesian optimization to find the best settings faster than trial-and-error).

!!! warning "Hyperparameters vs. MLOps"
    Changing a hyperparameter is a **Data Science** task. Setting up the pipeline to automate that change is an **MLOps** task.

---

## 🏪 Real-Life Example: Amazon's Delivery Routes

Imagine Amazon is training a model to predict delivery times.
*   **The Parameter:** The model learns that "Rain" usually adds 5 minutes to a route.
*   **The Hyperparameter:** The developer sets the **Learning Rate** to "0.01." 
    *   If the model gets a prediction wrong, it only changes its "Rain" rule by a tiny amount (0.01) so it doesn't overreact to one single weird rainy day. 
    *   This ensures the model stays stable over thousands of deliveries!

---
*Last Updated: Feb 2026*
