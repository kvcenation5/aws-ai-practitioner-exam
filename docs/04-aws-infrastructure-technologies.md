# AWS Infrastructure and Technologies

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

AWS offers a comprehensive suite of ML and generative AI services across three distinct layers. Understanding which service fits a specific use case is critical for the exam.

---

## 1. The AWS AI/ML Stack

AWS categorizes its services into a "stack" to help customers choose the right level of abstraction:

| Layer | Focus | Key Services |
| :--- | :--- | :--- |
| **Top Layer: AI Services** | Ready-to-use APIs for developers (no ML expertise needed). | Rekognition, Polly, Lex, Transcribe, etc. |
| **Middle Layer: ML Services** | Tools for building, training, and deploying custom models. | **Amazon SageMaker AI** |
| **Bottom Layer: Infrastructure** | High-performance hardware for expert researchers. | Trainium, Inferentia, GPUs. |

---

## 2. Amazon SageMaker AI

**Amazon SageMaker AI** is the primary service for traditional ML workflows. 

*   **Capabilities:** Building, training, and deploying ML models at scale.
*   **SageMaker JumpStart:** A hub within SageMaker to access pre-trained models (including FMs like Llama) for one-click deployment.
*   **SageMaker Canvas:** A visual, no-code interface for business analysts to build ML models.

!!! tip "Exam Tip: SageMaker AI vs. Bedrock"
    If the question asks for **full control** over model training and deployment, choose **SageMaker**. If it asks for **serverless access** to models via API, choose **Bedrock**.

---

## 3. Specialized AI Services (The "Ready-to-Use" Layer)

These services are pre-trained by AWS and available via API.

### Language & Text (NLP)
*   **Amazon Comprehend:** Uncovers insights and relationships in unstructured text (Sentiment analysis, entity recognition).
*   **Amazon Translate:** Neural machine translation for high-quality, fluent language conversion.
*   **Amazon Textract:** Extracts text, forms, and tables from scanned documents (goes beyond standard OCR).

### Speech & Chat
*   **Amazon Lex:** Powers conversational interfaces (Chatbots). Uses **ASR** (Automatic Speech Recognition) and **NLU** (Natural Language Understanding).
*   **Amazon Polly:** Converts text into lifelike speech (**TTS** - Text-to-Speech).
*   **Amazon Transcribe:** Converts speech into text (**ASR**). Supports real-time and batch processing.

### Vision & Search
*   **Amazon Rekognition:** Image and video analysis. Identifies objects, people, text, scenes, and detects inappropriate content.
*   **Amazon Kendra:** Intelligent enterprise search that finds content across multiple repositories using natural language questions.

### Industry/User Specific
*   **Amazon Personalize:** Creates individualized recommendations (Same tech used by Amazon.com).
*   **AWS DeepRacer:** A hands-on way to learn **Reinforcement Learning** through autonomous racing.

---

## 4. Generative AI Services

### Amazon Bedrock
A fully managed **serverless** service that makes Foundation Models (FMs) from AWS and AI startups (Anthropic, Meta, etc.) available through a single API.
*   **Exam Perspective:** Bedrock is the easiest way to build GenAI apps without managing infrastructure.

### Amazon Q
*   **Amazon Q Business:** An AI assistant that can answer questions and take actions based on your company's data.
*   **Amazon Q Developer:** Provides ML-powered code recommendations (formerly CodeWhisperer) for Java, Python, JS, etc.

---

## 5. Summary Table: AI/ML Service Comparison

| Service | Category | Key Function | Exam Keyword |
| :--- | :--- | :--- | :--- |
| **SageMaker AI** | Custom ML | Build/Train/Deploy custom models. | "Full Control", "Custom Model" |
| **Bedrock** | GenAI | Serverless API for Foundation Models. | "API-driven", "Serverless GenAI" |
| **Comprehend** | NLP | Sentiment and entity extraction. | "Insights from text" |
| **Rekognition** | Vision | Object/Face detection in images/video. | "Image analysis", "Computer Vision" |
| **Textract** | Documents | Extract data from tables/forms in PDFs. | "Beyond OCR", "Forms/Tables" |
| **Lex** | Chat | Build voice/text chatbots. | "NLU", "Conversational AI" |
| **Polly** | Speech | Text-to-Speech (TTS). | "Lifelike speech" |
| **Transcribe** | Speech | Speech-to-Text (ASR). | "Subtitles", "Meeting notes" |
| **Kendra** | Search | Intelligent search across repositories. | "Enterprise search", "Natural language Q&A" |
| **Personalize** | Recs | Personalized user recommendations. | "Recommendation engine" |
| **Q Developer** | Coding | AI-powered code suggestions. | "Speed up coding", "IDE integration" |

---

## 6. Infrastructure and Cost Considerations

*   **Security:** AWS uses a **Shared Responsibility Model**. AWS secures the infrastructure; you secure your data and model configurations.
*   **Privacy:** In Amazon Bedrock, your data is **not used** to train the base models.
*   **Cost Trade-offs:**
    *   **Proximity to data:** Regional availability impacts latency and cost.
    *   **Pricing Models:** On-demand (pay as you go) vs. Provisioned Throughput (for high-scale workloads).
    *   **Performance:** Higher performance (low latency) usually comes at a higher price point.

---
*Last Updated: Jan 2026*
