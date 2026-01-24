# Generative AI Fundamentals

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

## 1. What is Generative AI?
Generative AI is a subset of Deep Learning that can **create new content** (text, images, audio, code) based on the patterns it learned from existing data.

*   **Discriminative AI:** Predicts labels or categories (e.g., "Is this a spam email?").
*   **Generative AI:** Creates new data (e.g., "Write a response to this email.").

## 2. Foundation Models (FMs)
Large-scale models trained on vast amounts of data that can be adapted to a wide range of downstream tasks.

*   **Large Language Models (LLMs):** Foundation models focused on text (e.g., GPT-4, Claude, Llama).
*   **Scaling Laws:** The observation that model performance improves as you increase compute, data, and parameters.

## 3. The Transformer Architecture
The core technology behind modern GenAI. Its key innovation is **Self-Attention**, which allows the model to weigh the importance of different parts of the input relative to each other.

## 4. Key Terminology
*   **Prompt:** The input provided to the model (e.g., a question or instruction).
*   **Token:** The "chunks" of text the model processes (not always whole words).
*   **Context Window:** The maximum number of tokens a model can consider at once.
*   **Hallucination:** When a model generates factually incorrect but plausible-sounding information.
*   **Temperature:** A setting that controls the randomness/creativity of the output (0 = predictable, 1+ = creative/random).

## 5. Adapting Foundation Models
| Method | Description | Effort |
| :--- | :--- | :--- |
| **Prompt Engineering** | Crafting better inputs to get better outputs. | Low |
| **RAG (Retrieval-Augmented Generation)** | Giving the model access to external data to reduce hallucinations. | Medium |
| **Fine-Tuning** | Training the model on a smaller, task-specific dataset. | High |

## 6. Responsible AI
Since GenAI creates content, ethics and safety are critical:
*   **Toxicity:** Avoiding offensive or harmful content.
*   **Bias:** Ensuring the model doesn't favor one group over another.
*   **Transparency:** Disclosing when content is AI-generated.
*   **Security:** Protecting against prompt injection or data leakage.

## 7. AWS Generative AI Services
*   **Amazon Bedrock:** The easiest way to build GenAI apps using foundation models from AWS (Titan), Anthropic (Claude), Meta (Llama), etc., via API.
*   **Amazon Q:** A generative AI-powered assistant for work/AWS.
*   **SageMaker JumpStart:** A hub where you can find and deploy foundation models.
*   **AWS PartyRock:** A playground for learning how to build apps with Bedrock (non-coding).

---
*Last Updated: Jan 2026*
