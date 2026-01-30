# AWS Infrastructure and Technologies

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

AWS offers a comprehensive suite of ML and generative AI services that can help you unlock the full potential of these transformative technologies. In this lesson, you will learn about the various AI and ML services available on AWS, from text comprehension with Amazon Comprehend to code generation with Amazon Q Developer.

---

## 1. The AWS AI/ML Stack

AWS categorizes its services into a "stack" to help customers choose the right level of abstraction. AWS rapidly innovates across the AI and ML stack, offering comprehensive capabilities from infrastructure and tools to groundbreaking applications.

| Layer | Focus | Key Services |
| :--- | :--- | :--- |
| **Top Layer: AI Services** | Ready-to-use APIs for developers (no ML expertise needed). | Rekognition, Polly, Lex, Transcribe, etc. |
| **Middle Layer: ML Services** | Tools for building, training, and deploying custom models. | **Amazon SageMaker AI** |
| **Bottom Layer: Infrastructure** | High-performance hardware for expert researchers. | Trainium, Inferentia, GPUs. |

---

## 2. ML Frameworks & Amazon SageMaker AI

The ML frameworks layer plays a crucial role in the development and deployment of machine learning models. At the core of the frameworks layer is **Amazon SageMaker AI**.

### Amazon SageMaker AI
With SageMaker AI, you can build, train, and deploy ML models for any use case with fully managed infrastructure, tools, and workflows. 
*   **Fully Managed:** SageMaker AI removes the heavy lifting from each step of the ML process to make it easier to develop high-quality models. 
*   **Unified Toolset:** It provides all the components used for ML in a single toolset, so models get to production faster with much less effort and at lower cost.
*   **SageMaker JumpStart:** Helps you quickly get started with ML by providing a set of solutions for common use cases. It supports one-click deployment and fine-tuning of more than 150 popular open-source models (Llama, etc.).
*   **SageMaker Canvas:** A visual, no-code interface for business analysts to build ML models and generate predictions.

!!! info "Deep Dive"
    For a complete breakdown of all SageMaker tools—from Data Wrangler to Model Monitor—see the [SageMaker AI Features](10-sagemaker-ai.md) page.

!!! example "Practical Example: SageMaker AI"
    A bank uses SageMaker to build a custom fraud detection model by training it on millions of historical transactions to identify subtle patterns that indicate suspicious activity.


---

## 3. SageMaker AI vs. Amazon Bedrock

Choosing between these two is a common exam topic.

| Feature | Amazon SageMaker AI | Amazon Bedrock |
| :--- | :--- | :--- |
| **Model Type** | Custom ML & Deep Learning | Foundation Models (FMs) |
| **Primary Workflow** | Build, Train, Deploy (Full Lifecycle) | Consume via API (Serverless) |
| **Infrastructure** | **Managed Instances** (You choose GPU/CPU) | **Serverless** (No instances to manage) |
| **Control** | **High** (Complete control over code & env) | **Low** (Abstraction for ease of use) |
| **Customization** | Fine-tuning & Training from scratch | Fine-tuning & RAG (Retrieval-Augmented) |
| **Cost Model** | **Instance-based** (Pay by the hour) | **Token-based** (Pay per request/usage) |
| **Best For** | Data Scientists building unique models | Developers adding GenAI to apps quickly |

!!! info "Exam Perspective: The 'Flexibility' Trade-off"
    SageMaker offers the most **flexibility** for custom machine learning, while Bedrock offers the most **simplicity** for generative AI through pre-trained foundation models.

---

## 4. Specialized AI Services (The "Ready-to-Use" Layer)

These services provide developers with AI/ML capabilities without requiring extensive infrastructure management or specialized expertise.

### Language & Text (NLP)
*   **Amazon Comprehend:** Uses ML and natural language processing (NLP) to uncover insights and relationships in unstructured data.
    *   Identifies the language of the text.
    *   Extracts key phrases, places, people, brands, or events.
    *   Understands sentiment (positive/negative).
    *   Analyzes text using tokenization and parts of speech.
    *   Automatically organizes a collection of text files by topic.

!!! example "Practical Example: Comprehend"
    A customer support team uses Comprehend to automatically scan thousands of support tickets, identifying which ones express "negative" sentiment so they can prioritize angry customers.

*   **Amazon Translate:** A neural machine translation service that delivers fast, high-quality, and affordable language translation. It uses deep learning models to deliver more accurate and natural-sounding translations than traditional statistical algorithms.

!!! example "Practical Example: Translate"
    An e-commerce company uses Amazon Translate to instantly localize their product descriptions into 10 different languages, allowing them to launch in new countries in days instead of months.

*   **Amazon Textract:** Automatically extracts text and data from scanned documents. It goes beyond simple OCR to identify contents of fields in forms and information stored in tables.

!!! example "Practical Example: Textract"
    An insurance company uses Textract to automatically read medical claim forms. It doesn't just "see" the text; it understands which value belongs to "Policy Number" and which belongs to "Total Amount."


### Speech & Chat
*   **Amazon Lex:** A fully managed AI service to design, build, test, and deploy conversational interfaces (chatbots) using voice and text. It provides **ASR** (Automatic Speech Recognition) for converting speech to text and **NLU** (Natural Language Understanding) to recognize intent. Powered by the same technology as Amazon Alexa.

!!! example "Practical Example: Lex"
    An airline builds a chatbot using Lex that allows travelers to say "I want to change my flight" in natural language. Lex understands the **intent** and asks for the confirmation number.

*   **Amazon Polly:** Turns text into lifelike speech (**TTS**). Uses advanced deep learning technologies to synthesize speech that sounds like a human voice across dozens of languages.

!!! example "Practical Example: Polly"
    A news app uses Polly to create an "Audio Version" of its articles, allowing users to listen to the news during their morning commute with a voice that sounds like a real news anchor.

*   **Amazon Transcribe:** An automatic speech recognition (**ASR**) service for converting speech to text. 
    *   Supports common formats like WAV and MP3.
    *   Provides **time stamps** for every word.
    *   Supports live audio streaming for real-time transcription.
    *   Use cases: transcription of customer service calls, subtitles, and content analysis.

!!! example "Practical Example: Transcribe"
    A law firm uses Transcribe to automatically convert 100 hours of recorded legal depositions into searchable text format, saving weeks of manual typing.


### Vision & Search
*   **Amazon Rekognition:** Facilitates adding image and video analysis to your applications.
    *   Identify objects, people, text, scenes, and activities.
    *   Detect inappropriate content.
    *   Highly accurate facial analysis and facial search.
    *   Use cases: user verification, people counting, and public safety.

!!! example "Practical Example: Rekognition"
    A smart-home security system uses Rekognition to analyze video doorbells, notifying the owner only when a "Person" is detected rather than just a "Dog" or a "Car."

*   **Amazon Kendra:** An intelligent search service powered by ML. It reimagines enterprise search, helping employees find content even when it is scattered across multiple locations and repositories.

!!! example "Practical Example: Kendra"
    An employee at a large company asks, "What is our company's policy on remote work from Japan?" Kendra searches SharePoint, Box, and internal wikis to provide the specific answer instantly.


### Industry/User Specific
*   **Amazon Personalize:** Allows developers to create individualized recommendations for customers. 
    *   Uses an activity stream (page views, signups, purchases).
    *   Identifies what is meaningful, selects the right algorithms, and trains a customized model.

!!! example "Practical Example: Personalize"
    A streaming service uses Personalize to show a "Recommended for You" section where the movies shown are based on the specific genres and actors the user has watched in the past 30 days.

*   **AWS DeepRacer:** A 1/18th scale race car that provides a fun way to get started with **Reinforcement Learning (RL)**. RL learns complex behaviors without labeled data by optimizing for long-term goals.

!!! example "Practical Example: DeepRacer"
    A developer trains a virtual car in a simulator to stay on a track. The car gets a "reward" (+1) for staying in the center and a "penalty" (-1) for going off-track, eventually learning the optimal racing line.


---

## 5. Generative AI Services

### Amazon Bedrock
A fully managed service that makes Foundation Models (FMs) from Amazon and leading AI startups available through an API.
*   **Serverless Experience:** Quickly experiment, privately customize with your own data, and deploy into AWS applications without managing infrastructure.

!!! example "Practical Example: Bedrock"
    A marketing agency uses Bedrock to access the **Claude 3** model. They provide their brand guidelines as context (RAG) and the model generates personalized email campaigns for thousands of their clients.


### Amazon Q
*   **Amazon Q Business:** Helps get fast, relevant answers to questions, solve problems, and generate content using company information repositories and enterprise systems.
*   **Amazon Q Developer:** Improves developer productivity by providing ML-powered code recommendations (Java, JS, Python, etc.). It can generate entire functions and logical blocks of code (10–15+ lines).

!!! example "Practical Example: Amazon Q"
    A DevOps engineer asks Amazon Q Business, "Why is my Lambda function timing out?" Q analyzes the logs and configuration to suggest increasing the memory or timeout setting.


---

## 6. Summary Table: AI/ML Service Comparison

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

## 7. Infrastructure and Cost Considerations

AWS provides a secure and compliant infrastructure for building AI applications. AWS uses a **Shared Responsibility Model**.

### Cost Trade-offs
When working with AI and ML services, several factors impact cost:
*   **Responsibility & Maintenance:** Managed services (Bedrock) vs. Infrastructure control (SageMaker).
*   **Pricing Models:** On-demand (pay per request) vs. Provisioned Throughput (guaranteed capacity).
*   **Regional Coverage:** Costs can vary by region and proximity to data.
*   **Performance:** Higher throughput and lower latency requirements typically increase costs.

---
*Last Updated: Jan 2026*
