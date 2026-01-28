# Prompt Engineering Essentials

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Prompt engineering is the process of localizing and optimizing inputs (prompts) to guide Foundation Models (FMs) toward generating high-quality, accurate, and relevant outputs. It is the fastest way to harness the power of GenAI without the cost of fine-tuning.

---

## 1. Anatomy of a Prompt

A well-structured prompt typically consists of four key elements. While not every prompt needs all four, including them significantly improves output quality.

| Element | Description | Example |
| :--- | :--- | :--- |
| **Instructions** | The specific task for the model to perform. | "Summarize this article." |
| **Context** | External information or constraints to guide the model. | "This summary is for a technical blog post." |
| **Input Data** | The specific data you want processed. | "[Insert article text here]" |
| **Output Indicator** | The desired format or starting point of the response. | "Summary in 3 bullet points:" |

!!! tip "Exam Tip: The 'AnyCompany' Scenario"
    If you ask a model to "Generate a market report" without context, it might give you a report on Smart Homes when you actually work in Finance. **Context** is the most critical missing piece in vague prompts.

---

## 2. Negative Prompting

Negative prompting guides the model by specifying what **not** to include.
*   **Purpose:** Prevents biased language, explicit content, or specific formatting styles.
*   **Example:** "Generate a travel itinerary for Tokyo. **Do not** include any activities involving high heights or roller coasters."

---

## 3. Inference Parameters

Inference parameters are "knobs" you can turn to adjust how the model generates text. 

### A. Randomness and Diversity
These parameters control how "creative" or "focused" the model is.

*   **Temperature (0.0 to 1.0):**
    *   **Low (0.2):** Focused, conservative, and predictable. Best for factual tasks.
    *   **High (1.0):** Diverse, creative, and unpredictable. Best for brainstorming/storytelling.
*   **Top P (Nucleus Sampling):** Limits the model to a "pool" of words whose cumulative probability reaches P. 
    *   *Example:* Top P = 0.25 means the model only considers the most certain words.
*   **Top K:** Limits the model to the top **K** most probable next words, regardless of their total probability.

### B. Length and Termination
*   **Max Length:** Limits the number of tokens generated to prevent resource exhaustion.
*   **Stop Sequences:** Specific characters or tokens (like `\n` or `End_of_Topic`) that tell the model to stop typing immediately.

!!! info "Exam Perspective: Predictability"
    If an exam question asks how to make a model more **reproducible** or **factual**, the answer is usually to **Decrease Temperature**.

---

## 4. Prompting Techniques

### Zero-Shot Prompting
Asking the model to perform a task without giving it any examples. 
*   *Prompt:* "Translate 'Hello' to French."
*   *Usage:* Relies entirely on the pre-trained knowledge of the FM.

### Few-Shot Prompting
Providing the model with a few examples (shots) of the desired input-output behavior.
*   *Prompt:* 
    *   "Great pen" => Positive
    *   "I hate this battery" => Negative
    *   "The screen is okay" =>
*   *Usage:* Helps the model understand complex formatting or specific domain styles.

### Chain-of-Thought (CoT) Prompting
Asking the model to "think step-by-step" to solve complex reasoning or math problems.
*   *Prompt:* "If I have 5 apples and buy 2 more, how many do I have? **Think step by step.**"
*   *Usage:* Significantly reduces errors in logic and multi-step calculations.

---

## 5. Best Practices Checklist

1.  **Be Clear and Concise:** Avoid ambiguous language.
2.  **Use Directives:** Explicitly state if you want a "Summary," "Poem," or "JSON object."
3.  **Start with Interrogations:** Use "Who, What, Where, When, Why, How."
4.  **Consider the End:** Sometimes placing the instruction at the very end of a long prompt helps the model focus.
5.  **Break it Down:** If a task is too complex, split it into multiple sub-prompts.

---

## 6. Real-Life Example: The Refined Prompt

| Version | Prompt | Result |
| :--- | :--- | :--- |
| **Bad** | "Generate a market report." | Vague, generic, irrelevant industry. |
| **Good** | **Parameters:** Temp 0.9. **Prompt:** "Generate a comprehensive market analysis report for the finance industry targeting SMBs. Structure: 1. Summary, 2. Overview, 3. Competition. Tone: Professional." | Focused, structured, and industry-specific. |

---
*Last Updated: Jan 2026*
