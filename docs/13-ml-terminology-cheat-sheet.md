# ML Model Terminology Cheat Sheet

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

This page is an "Executive Summary" of common machine learning models and terms. You don't need to know the complex math behind them, but you should be able to recognize their **primary purpose** to help you eliminate wrong answers in the exam.

---

## 📝 The "Big Three" for Generative AI

| Model | Full Name | Exam Trigger / Intent |
| :--- | :--- | :--- |
| **GPT** | Generative Pre-trained Transformer | **Generating human text or code** based on prompts. |
| **BERT** | Bidirectional Encoder Representations from Transformers | Reads text in **two directions**. Great for **translation** and understanding context. |
| **GAN** | Generative Adversarial Network | Generates **synthetic data** (images, videos, sounds). Used for **Data Augmentation** to fix imbalanced datasets. |

---

## 🖼️ Vision, Audio, and Sequential Models

| Model | Primary Category | Exam Trigger / Intent |
| :--- | :--- | :--- |
| **ResNet** | **Images** | A Deep CNN (Convolutional Neural Network) used for **object detection and facial recognition**. |
| **WaveNet** | **Audio** | Generates **raw audio waveforms**. Used in **speech synthesis** (Text-to-Speech). |
| **RNN** | **Sequential** | Recurrent Neural Network. Geared for **sequential data** like **time series** or speech recognition. |

---

## 📊 Traditional ML Algorithms

| Algorithm | Full Name | Exam Trigger / Intent |
| :--- | :--- | :--- |
| **XGBoost** | Extreme Gradient Boosting | Highly optimized gradient boosting for **regression** and classification on tabular data. |
| **SVM** | Support Vector Machine | Classic algorithm used for both **classification and regression**. |
| **kNN** | k-Nearest Neighbors | Predicts by looking at **closest neighbors** (Majority Vote for Classification, Average for Regression). |

---

## 🏘️ ELI5: k-Nearest Neighbors (kNN)

Think of kNN as the **"Peer Pressure"** algorithm. It doesn't really "learn" from a textbook; it just looks at who is standing next to it.

*   **How it works:** To classify a new point, it finds the **$k$** closest points (neighbors).
*   **Classification:** It chooses the label held by the **majority** of its neighbors.
*   **Regression:** It calculates the **average** value of its neighbors.

!!! warning "Exam Secret"
    If the exam describes an algorithm that **"doesn't have a formal training phase"** or **"makes predictions by directly comparing new data to existing samples at runtime,"** the answer is **kNN**.

---

## 💡 Quick Process-of-Elimination Guide

If the exam question mentions... | Think of...
:--- | :---
**"Synthetic Data"** or **"Data Augmentation"** | **GAN**
**"Facial Recognition"** or **"Object Detection"** | **ResNet**
**"Audio Synthesis"** or **"Waveforms"** | **WaveNet**
**"Sequential Data"** or **"Time Series"** | **RNN**
**"Bidirectional Context"** or **"Translation"** | **BERT**

---
*Last Updated: Feb 2026*
