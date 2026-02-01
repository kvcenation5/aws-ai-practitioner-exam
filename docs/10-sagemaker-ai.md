# Amazon SageMaker AI Features

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Amazon SageMaker AI is a fully managed ML service. In a single unified visual interface, you can perform the following tasks:
1.  **Collect and prepare data.**
2.  **Build and train machine learning models.**
3.  **Deploy the models and monitor the performance of their predictions.**

---

## 🏗️ SageMaker AI Feature Categories

SageMaker AI provides specialized tools for every stage of the machine learning lifecycle.

### 1. Data Preparation
*   **Amazon SageMaker Data Wrangler**
    A low-code/no-code (LCNC) tool to import, prepare, transform, featurize, and analyze data through a web interface. You can also add custom Python scripts for advanced workflows.
*   **SageMaker Studio Classic Integration**
    Built-in integration with **Amazon EMR** and **AWS Glue** for large-scale interactive data preparation and ML workflows within notebooks.
*   **SageMaker Processing API**
    Allows running scripts and notebooks to process, transform, and analyze datasets. Supports frameworks like scikit-learn, MXNet, and PyTorch.

### 2. Feature Management
*   **Amazon SageMaker Feature Store**
    A purpose-built repository to create, share, and manage features for ML development. It allows data to be ingested, stored, retrieved, and served to ML models for inference.

### 3. Model Building & Training
*   **Training Jobs**
    SageMaker launches ML compute instances, uses your code/dataset to train the model, and saves artifacts in **Amazon S3**.
*   **Amazon SageMaker Canvas**
    The primary LCNC option. It allows business analysts to build ML models and generate predictions **without writing any code**.
*   **Amazon SageMaker JumpStart**
    A hub for pre-trained, open-source models (Foundation Models, etc.) that you can deploy or fine-tune with one click.

### 4. Model Evaluation & Tuning
*   **Amazon SageMaker Experiments**
    A tool to track and compare multiple combinations of data, algorithms, and parameters to observe their impact on model accuracy.
*   **Automatic Model Tuning (Hyperparameter Tuning)**
    Finds the best version of your model by running multiple training jobs with different combinations of hyperparameters and measuring success against a chosen metric.

### 5. Deployment & Inference
*   SageMaker provides a broad selection of ML infrastructure (CPU/GPU/Inferentia) and deployment options (Real-time, Batch, Serverless, Asynchronous) to meet various latency and cost requirements.

### 6. Monitoring & Optimization
*   **Amazon SageMaker Model Monitor**
    Observes the quality of production models. It detects violations of user-defined thresholds for:
    - **Data Quality:** Changes in data distribution.
    - **Model Quality:** Accuracy drift.
    - **Bias Drift:** Emergence of bias over time.
    - **Feature Attribution Drift:** Changes in which features contribute most to predictions.

---

## 📂 Sources of ML Models

SageMaker AI provides multiple ways to build models, ranging from "zero-effort" to "full customization."

| Method | Level of Effort | Description |
| :--- | :--- | :--- |
| **Pre-trained Models** | **Least Effort** | Models ready to deploy or fine-tune immediately using **SageMaker JumpStart**. |
| **Built-in Algorithms** | **Medium Effort** | Highly optimized algorithms provided by AWS that scale automatically for large datasets. |
| **Pre-made Framework Images** | **High Effort** | Use pre-configured Docker images for common frameworks like **TensorFlow, PyTorch, scikit-learn, MXNet, or Chainer**. |
| **Custom Docker Images** | **Most Effort** | Build and bring your own Docker image with specific packages and software required for your unique model. |

---

## 🧮 SageMaker AI Built-in Algorithms (Cheat Sheet)

SageMaker AI provides algorithms for different categories of machine learning problems. This is a shortlist of the most common algorithms. Refer to the SageMaker AI documentation for a complete list and further details.

### 1. Supervised Learning
SageMaker AI provides several built-in general-purpose algorithms that you can use for either classification or regression problems.

![SageMaker Supervised Learning Algorithms](assets/sagemaker-supervised-algorithms.png)

Key Supervised Algorithms:
*   **Linear Learner:** Used for linear regression or classification.
*   **XGBoost:** An optimized gradient boosting library.
*   **Factorization Machines:** Often used for high-dimensional data like recommendation systems.
*   **K-Nearest Neighbors (KNN):** Simple, proximity-based prediction.

### 2. Unsupervised Learning
SageMaker AI provides several built-in algorithms that can be used for unsupervised learning tasks such as clustering, dimension reduction, topic modeling, and anomaly detection.

![SageMaker Unsupervised Learning Algorithms](assets/sagemaker-unsupervised-algorithms.png)

Key Unsupervised Algorithms:
*   **K-means:** Used for clustering similar data points into different groups.
*   **Latent Dirichlet Allocation (LDA):** Used for **Topic Modeling** and finding patterns in high-dimensional datasets.
*   **Object2Vec:** Creates **Embeddings** (low-dimensional vectors) for complex objects like words or users to measure similarity.
*   **Principal Component Analysis (PCA):** Reduces the number of features (**Dimensionality Reduction**) while retaining as much information as possible.
*   **Random Cut Forest (RCF):** Specifically designed for **Anomaly Detection** in streaming or batch data.
*   **IP Insights:** An anomaly detection algorithm that learns patterns in IP addresses to identify suspicious activity.

### 3. Image Processing & Computer Vision
SageMaker AI provides image processing algorithms for image classification, object detection, semantic segmentation, and time series forecasting.

![SageMaker Image Processing Algorithms](assets/sagemaker-image-processing.png)

Key Vision & Time Series Algorithms:
*   **Image Classification:** Uses frameworks like **MXNet** and **TensorFlow** (e.g., ResNet, ImageNet) to identify the primary subject of an image.
*   **Object Detection:** Identifies and locates multiple objects within an image or video frame.
*   **Semantic Segmentation:** Provides pixel-level classification to identify the exact boundaries of objects. Key methods include **FCN** (Fully Convolutional Network), **PSP** (Pyramid Scene Parsing), and **DeepLab V3**.
*   **DeepAR:** A supervised learning algorithm for forecasting one-dimensional **Time Series** data (e.g., predicting future sales or stock levels).

### 4. Text Analysis & NLP
Algorithms tailored for analyzing textual documents:
*   **Classification & Summarization:** Organizing documents or generating short versions.
*   **Topic Modeling:** Discovering themes within text.
*   **Language Transcription & Translation:** Converting speech to text or one language to another.

---
*Last Updated: Jan 2026*
