# Generative AI Fundamentals

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Generative AI (GenAI) is a subset of deep learning that creates new content (text, images, audio, etc.) by learning patterns from massive datasets. Its recent surge is driven by massive investments in compute resources, large-scale data, and the willingness of organizations to develop "big ideas."

---

## 1. Foundation Models (FMs)

Generative AI is powered by **Foundation Models**. These are models pretrained on internet-scale, unlabeled data.

*   **One Model, Many Tasks:** Unlike traditional ML which requires a new model for every task, a single FM can be adapted for text generation, summarization, image creation, chatbot interactions, and more.
*   **Starting Point:** FMs serve as the base for building specialized models for specific industries (like medical or legal).

### Amazon Bedrock
AWS provides access to high-performing FMs through **Amazon Bedrock**. It hosts models from:
*   **Amazon** (Titan)
*   **Anthropic** (Claude series)
*   **Meta** (Llama series)
*   **Mistral AI**
*   **Stability AI** (Stable Diffusion)
*   **AI21 Labs**
*   **Cohere**

---

## FM lifecycle

### 1. Data selection
Unlabeled data can be used at scale for pre-training because it is much easier to obtain compared to labeled data. Unlabeled data includes raw data, such as images, text files, or videos, with no meaningful informative labels to provide context. FMs require training on massive datasets from diverse sources.

### 2. Pre-training
Although traditional ML models rely on supervised, unsupervised, or reinforcement learning patterns, FMs are typically pre-trained through self-supervised learning. With self-supervised learning, labeled examples are not required. Self-supervised learning makes use of the structure within the data to autogenerate labels.

During the initial pre-training stage, the FM's algorithm can learn the meaning, context, and relationship of the words in the datasets. For example, the model might learn whether drink means beverage, the noun, or swallowing the liquid, the verb.

After the initial pre-training, the model can be further pre-trained on additional data. This is known as continuous pre-training. The goal is to expand the model's knowledge base and improve its ability to understand and generalize across different domains or tasks.

### 3. Optimization
Pre-trained language models can be optimized through techniques like prompt engineering, retrieval-augmented generation (RAG), and fine-tuning on task-specific data. These methods will vary in complexity and cost and will be discussed later in this lesson.

### 4. Evaluation
Whether or not you fine-tune a model or use a pre-trained model off the shelf, the next logical step is to evaluate the model. An FM's performance can be measured using appropriate metrics and benchmarks. Evaluation of model performance and its ability to meet business needs is important.

### 5. Deployment
When the FM meets the desired performance criteria, it can be deployed in the target production environment. Deployment can involve integrating the model into applications, APIs, or other software systems.

### 6. Feedback and continuous improvement
After deployment, the model's performance is continuously monitored, and feedback is collected from users, domain experts, or other stakeholders. This feedback, along with model monitoring data, is used to identify areas for improvement, detect potential biases or drift, and inform future iterations of the model. The feedback loop permits continuous enhancement of the foundation model through fine-tuning, continuous pre-training, or re-training, as needed.

---

## 3. Types of Generative Models

### Large Language Models (LLMs)
Most modern LLMs use the **Transformer** architecture. They understand relationships between words by processing them as:
*   **Tokens:** The basic units of text (words, phrases, or characters).
*   **Embeddings & Vectors:** Mathematical representations that capture the meaning and relationship of tokens.

### Diffusion Models
A deep learning architecture that starts with pure noise and gradually adds meaningful information to create a coherent output.
*   **Forward Diffusion:** Adding noise until only static remains.
*   **Reverse Diffusion (Denoising):** Gradually removing noise until a new image or text emerges.

### Multimodal Models
These models can process and generate multiple modes of data **simultaneously**.
*   **Example:** Inputting an image + text and receiving a new image + descriptive caption.
*   **Use cases:** Automated video captioning, intelligent Q&A with visual info.

### Other Models
*   **GANs (Generative Adversarial Networks):** Two networks (Generator and Discriminator) competing to create realistic data.
*   **VAEs (Variational Autoencoders):** Encode data into a latent space and decode it back to create new variations.

---

## 4. Optimizing Model Outputs

The FM lifecycle includes an optimization phase to tailor the model to specific needs.

### 1. Prompt Engineering (Fastest & Lowest Cost)
Developing and optimizing "Instructions" to guide the model's behavior.
*   **Elements of a good prompt:**
    *   **Instructions:** The task description.
    *   **Context:** External info to guide the model.
    *   **Input Data:** The data the model should process.
    *   **Output Indicator:** The desired format (e.g., "Summarize in 2 sentences").

### 2. Fine-Tuning (Changes Model Weights)
A supervised learning process involving smaller, specific datasets to adjust the model's internal parameters (weights).
*   **Instruction Fine-Tuning:** Using examples of how the model should respond to commands.
*   **RLHF (Reinforcement Learning from Human Feedback):** Aligning the model with human preferences using reward signals.

### 3. RAG (Retrieval-Augmented Generation)
Supplies domain-relevant data as "context" to the model without changing its internal weights.
*   **How it works:** It retrieves relevant documents from an external source and provides them to the model along with the user's prompt.
*   **Comparison:** Unlike fine-tuning, RAG **does not change model weights**.

---

## 5. Key Terminology

| Term | Definition |
| :--- | :--- |
| **Hallucination** | When a model generates factually incorrect but plausible-sounding info. |
| **Context Window** | The limit of how many tokens a model can "remember" or process at once. |
| **Temperature** | Controls randomness (0 = predictable/factual, 1+ = creative/random). |
| **Tokens** | Small units of text that provide standardization for model processing. |

---
*Last Updated: Jan 2026*
