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

| Algorithm | Exam Trigger / Intent |
| :--- | :--- |
| **XGBoost** | Extreme Gradient Boosting. A highly optimized implementation of gradient boosting used for **regression** and classification on tabular data. |
| **SVM** | Support Vector Machine. A classic algorithm used for both **classification and regression**. |

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
