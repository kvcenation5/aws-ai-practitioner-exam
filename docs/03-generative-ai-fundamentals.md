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

## 2. The Foundation Model (FM) Lifecycle

Developing and deploying effective and reliable foundation models involves a comprehensive process:

### 1. Data Selection
*   **Unlabeled Data:** Used at scale for pre-training because it is much easier to obtain than labeled data. 
*   **Massive Datasets:** FMs require training on vast, diverse sources (images, text, video) to learn broad representations.

### 2. Pre-training
*   **Self-supervised Learning:** Unlike traditional ML, FMs use self-supervised learning where the algorithm makes use of the structure within the data to autogenerate labels.
*   **Meaning & Context:** During this stage, the model learns relationships (e.g., whether "drink" is a noun or a verb).
*   **Continuous Pre-training:** Further training on additional data to expand the model's knowledge base and improve generalization across domains.

### 3. Optimization
Pre-trained models are tailored to specific tasks using:
*   **Prompt Engineering:** Designing instructions to guide model behavior.
*   **RAG (Retrieval-Augmented Generation):** Supplying external data as context.
*   **Fine-tuning:** Training on task-specific, labeled data to adjust model weights.

### 4. Evaluation
*   **Metrics & Benchmarks:** Measuring performance against business needs and safety standards.
*   **Validation:** Ensuring the model meets desired performance criteria before moving forward.

### 5. Deployment
*   **Integration:** Moving the FM into a production environment by integrating it into applications, APIs, or software systems.

### 6. Feedback & Continuous Improvement
*   **Monitoring:** Tracking performance, detecting potential biases, or "drift" in the real world.
*   **Feedback Loop:** Using input from users and experts for future iterations (fine-tuning, continuous pre-training, or re-training).

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
