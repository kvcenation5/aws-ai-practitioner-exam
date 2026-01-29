# Prompt Engineering Essentials

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Prompt engineering is the fastest way to harness the power of GenAI. By interacting with a model through a series of questions, statements, or instructions, you can adjust output behavior based on specific context.

---

## 1. Benefits and Importance
Why bother with prompt engineering?
*   **Greater Developer Control:** Fine-tune outputs without changing model weights.
*   **Improved User Experience:** Deliver more relevant, accurate, and safe responses.
*   **Enhanced Capabilities:** Helps FMs perform tasks like classification, code generation, and complex reasoning.
*   **Safety & Bias Mitigation:** Helps bolster safety measures and reduce problematic outputs.

!!! note "Hallucination Reduction"
    To reduce hallucinations, use prompt optimization combined with techniques like **Retrieval Augmented Generation (RAG)** to provide the model access to grounded data.


---

## 2. Elements of a Prompt
A prompt's form depends on the task. A complete prompt often includes:

*   **Instructions:** The task for the model to perform.
*   **Context:** External information to guide the model (e.g., "I work in finance").
*   **Input Data:** The raw content for which you want a response.
*   **Output Indicator:** The desired type or format of the output.

### Example: Restaurant Review Summary
> **Context:** The following is text from a restaurant review:  
> **Input Data:** "I finally got to check out Alessandro’s Brilliant Pizza... [detailed review]"  
> **Instruction:** Summarize the above restaurant review in one sentence.  
> **Output:** Alessandro's Brilliant Pizza is a fantastic restaurant in Seattle with a beautiful view and delicious food.

!!! tip "Exam Tip: Component Significance"
    Without the **Instruction**, the model doesn't know what to do with the text. Without the **Input Data**, it has nothing to operate on. The **Context** (e.g., "The following is a review") provides the keywords that guide model focus.


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
| **Top P** | 0 to 1 | **Nucleus Sampling:** Limits choices to a subset of words whose **cumulative probability sum** reaches P. (It is NOT a percentage of the total dictionary). |

| **Top K** | 1+ | Limits choices to a fixed number of most likely words (e.g., Top K 50 = always pick from top 50, regardless of probability %). |

### Length & Control (Response Termination)
*   **Maximum Length (Max Tokens):** 
    - This is a **hard limit** on the total number of tokens (words/parts of words) the model can generate for a single response.
    - **Why it matters:** It prevents the model from generating infinite text, saves compute costs (Bedrock charges per token), and reduces latency.
    - **Trade-off:** If set too low, the model's response will be **truncated** (cut off in the middle of a sentence).
*   **Stop Sequences:** 
    - These are specific character strings that tell the model to **stop typing immediately** as soon as it generates them.
    - **Common Examples:** Newline characters (`\n`), specific markers like `###`, `User:`, or `End of Response`.
    - **Best Practice:** When doing **Few-Shot prompting**, use a stop sequence like `###` at the end of each example. This prevents the model from "making up" additional fake examples after it completes your actual request.


!!! tip "The 'Big Three' Comparison"
    *   **Top K (Selection by Rank):** Limits the model to a fixed number of the most likely words. (e.g., "Only look at the top 50 choices").
    *   **Top P (Selection by Weight):** Limits the model to a "nucleus" of words that add up to a specific probability. (e.g., "Look at as many words as it takes to reach 90% certainty").
    *   **Max Tokens (Selection by Volume):** Limits how long the response can be. (e.g., "Stop talking after 200 words").

### Why use both Top K and Top P?
Most advanced models use both in a **pipeline** (Top K is usually applied first):
1.  **Top K acts as a "Hard Cap":** It prevents the model from ever looking at the "long tail" of low-probability words, even if Top P hasn't been reached yet.
2.  **Top P acts as a "Dynamic Filter":** It narrows the Top K selection even further when the model is very confident, ensuring the response stays relevant.


---

### 5. Prompt Latency
Latency is the time it takes for a model to generate a response. In the context of the AWS AI Practitioner exam, you should understand what drives latency and how to optimize it.

#### Factors Influencing Latency:
*   **Prompt Length (Input Tokens):** Larger prompts (e.g., long RAG context or massive few-shot examples) increase the "time to first token" (TTFT) because the model has to process all input before it starts generating.
*   **Generation Length (Output Tokens):** This is typically the **biggest factor**. Because LLMs generate text one token at a time, a 1,000-token response will take significantly longer than a 50-token response.
*   **Model Size/Complexity:** Larger, more "intelligent" models (like Claude 3 Opus) have higher latency than smaller, faster models (like Claude 3 Haiku or Amazon Nova Micro).
*   **Inference Parameters:** While Temperature doesn't affect speed, setting a high **Max Tokens** limit can lead to longer (and thus slower) responses.

#### Strategies to Reduce Latency:
1.  **Use Streaming:** Show the output to the user as it is being "typed" by the model. This doesn't change the total time but drastically reduces **Perceived Latency**.
2.  **Model Selection:** Choose "smaller/faster" models for simple tasks like classification or summarization.
3.  **Prompt Optimization:** Keep your prompts clear and avoid unnecessary "rambling" in the instructions.
4.  **Provisioned Throughput (Bedrock):** For high-traffic applications, use Provisioned Throughput to ensure consistent performance and lower latency.

!!! info "What does NOT impact latency?"
    In the exam, look out for these "distractor" options. These typically do **not** increase the computational time per token:
    *   **Temperature:** Whether you set it to 0 or 1, the model performs the same amount of math.
    *   **Top P / Top K:** These are simple filters applied *after* the model has already calculated the next alternatives.
    *   **The specific language (English vs. French):** The model processes tokens, not "languages" in a way that changes GPU speed.
    *   **Presence of Stop Sequences:** These actually *reduce* total latency by stopping the model early.


---

## 6. Best Practices: "Bad vs. Good"

| Rule | Bad Prompt | Good Prompt (Refined) |
| :--- | :--- | :--- |
| **Clear & Concise** | "Compute the sum total of the subsequent sequence..." | "What is the sum of these numbers: 4, 8, 12, 16?" |
| **Include Context** | "Summarize this article." | "Provide a summary of this article to be used in a blog post." |
| **Use Directives** | "What is the capital?" | "What is the capital of New York? Provide the answer in a full sentence." |
| **Consider Output** | "Calculate the area of a circle." | "Calculate the area of a circle with a radius of 3. Round to the nearest integer." |
| **Start with Interrogation** | "Summarize this event." | "Why did this event happen? Explain in three sentences." |
| **Provide Examples** | "Determine sentiment: [Post]" | "post: 'great' => Positive. post: 'bad' => Negative. [Post] =>" |

---

## 7. Prompt Engineering Techniques

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

### Advanced Prompting Techniques
Beyond basic shots, these techniques help with extreme complexity:

*   **Tree-of-Thought (ToT):** Generalizes CoT by allowing the model to generate multiple possible "next steps" and using a tree search to explore the best path.
*   **Maieutic Prompting:** Prompts the model for an answer *and* an explanation, then prompts it to explain parts of that explanation to prune inconsistencies.
*   **Generated Knowledge:** Prompt the model to first "list relevant facts" about a topic before completing the main task (e.g., "List facts about climate change, then write an essay").
*   **Least-to-Most:** Prompt the model to list sub-problems first, then solve them in sequence.
*   **Self-Refinement:** Model drafts a solution, critiques it, and rewrites it iteratively based on the critique.

!!! warning "Model Specifics (Amazon Bedrock)"
    *   **Anthropic Claude:** Use XML-style tags like `<example></example>` to separate sections.
    *   **Delimiters:** Use clear markers like `H:` (Human) and `A:` (Assistant) or `###` to prevent the model from confusing instructions with data.


---

## 8. The AnyCompany Scenario (Final Refined Prompt)
The student starts with a vague prompt but refines it based on the course:

*   **Initial:** "Generate a market analysis report."
*   **Refined:** "Generate a comprehensive market analysis report for the finance industry for an audience of SMBs. Structure: 1. Summary, 2. Overview, 3. Competition... Tone: Professional."
*   **Result:** High-quality, tailored output that addresses the specific goals of a finance firm.

---
## 9. References & Further Reading
*   [Amazon Bedrock Prompt Engineering Guidelines](https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-engineering-guidelines.html)
*   [AWS: What is Prompt Engineering?](https://aws.amazon.com/what-is/prompt-engineering/)

---
*Last Updated: Jan 2026*
