# Prompt Engineering Essentials

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Prompt engineering is the fastest way to harness the power of GenAI. By interacting with a model through a series of questions, statements, or instructions, you can adjust output behavior based on specific context.

---

## 1. Benefits of Effective Prompting
*   **Enhance Capabilities:** Bolsters the model's performance and safety measures.
*   **Domain Knowledge:** Equips models with specific knowledge without modifying parameters or fine-tuning.
*   **Comprehension:** Helps developers fully understand a model's potential.
*   **Quality:** Higher-quality inputs directly lead to higher-quality outputs.

---

## 2. Elements of a Prompt
A prompt's form depends on the task. A complete prompt often includes:

*   **Instructions:** The task for the model to perform.
*   **Context:** External information to guide the model (e.g., "I work in finance").
*   **Input Data:** The raw content for which you want a response.
*   **Output Indicator:** The desired type or format of the output.

### Example: Inventory Management
> **Prompt:** Given a list of customer orders and available inventory, determine which can be fulfilled. This task is essential for ecommerce businesses.  
> **Orders:** Product A (5 units)...  
> **Inventory:** Product A (8 units)...  
> **Fulfillment status:** 
*   **Instructions:** Determine fulfillment/restock needs.
*   **Context:** Ecommerce/retail context.
*   **Input Data:** The specific order/inventory numbers.
*   **Output Indicator:** The phrase "Fulfillment status:"

---

## 3. Negative Prompting
Used to guide the model away from specific content or behaviors.
*   **Example:** Preventing hate speech, explicit content, or biased language in a chatbot.
*   **Tip:** It's often easier to tell a model what **not** to do than to list every acceptable thing.

---

## 4. Inference Parameters (The "Knobs")

### Randomness & Diversity
| Parameter | Range | How it Works |
| :--- | :--- | :--- |
| **Temperature** | 0 to 1 | **Low (0.2):** Focused, conservative. **High (1.0):** Creative, diverse but potentially less coherent. |
| **Top P** | 0 to 1 | Limits choices to words that make up a cumulative probability (e.g., Top P 0.25 = top 25% of likely words). |
| **Top K** | 1+ | Limits choices to a fixed number of most likely words (e.g., Top K 50 = always pick from top 50, regardless of probability %). |

### Length & Control
*   **Maximum Length:** Limits tokens to prevent resource exhaustion or "hallucination loops."
*   **Stop Sequences:** Special tokens that tell the model to terminate generation immediately (e.g., a "User:" token in a chat).

---

## 5. Best Practices: "Bad vs. Good"

| Rule | Bad Prompt | Good Prompt (Refined) |
| :--- | :--- | :--- |
| **Clear & Concise** | "Compute the sum total of the subsequent sequence..." | "What is the sum of these numbers: 4, 8, 12, 16?" |
| **Include Context** | "Summarize this article." | "Provide a summary of this article to be used in a blog post." |
| **Use Directives** | "What is the capital?" | "What is the capital of New York? Provide the answer in a full sentence." |
| **Consider Output** | "Calculate the area of a circle." | "Calculate the area of a circle with a radius of 3. Round to the nearest integer." |
| **Start with Interrogation** | "Summarize this event." | "Why did this event happen? Explain in three sentences." |
| **Provide Examples** | "Determine sentiment: [Post]" | "post: 'great' => Positive. post: 'bad' => Negative. [Post] =>" |

---

## 6. Prompt Engineering Techniques

### Zero-Shot Prompting
Relies on the model's general knowledge. No examples provided.
*   **Tip:** Larger models (like Claude 3 or Llama 3) perform better at zero-shot tasks.

### Few-Shot Prompting
Providing contextual examples (One-shot = 1 example, Few-shot = multiple).
*   **Tip:** Ensure examples are representative and diverse. Too many examples can introduce "noise."

### Chain-of-Thought (CoT) Prompting
Divides intricate reasoning into smaller, intermediary steps.
*   **Keyword:** Use the phrase **"Think step by step"** to initiate logic loops.
*   **Example:** Math problems or multi-layer logic (e.g., comparing deposit costs for two different services).

---

## 7. The AnyCompany Scenario (Final Refined Prompt)
The student starts with a vague prompt but refines it based on the course:

*   **Initial:** "Generate a market analysis report."
*   **Refined:** "Generate a comprehensive market analysis report for the finance industry for an audience of SMBs. Structure: 1. Summary, 2. Overview, 3. Competition... Tone: Professional."
*   **Result:** High-quality, tailored output that addresses the specific goals of a finance firm.

---
*Last Updated: Jan 2026*
