# Model Evaluation and Metrics

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Evaluating an AI model correctly is critical for ensuring it is reliable, safe, and cost-effective. The metrics we use depend on whether we are looking at traditional ML (Classification/Regression) or Generative AI (Language/Images).

---

## 1. Generative AI Metrics (LLMs)

### Perplexity (PPL)
Perplexity measures how well a probability model predicts a sample. 
*   **Conceptual Meaning:** "How confused is the model?"
*   **Scoring:** **Lower is better.** A lower perplexity means the model is more confident in its predictions.
*   **Key Fact:** It is an *intrinsic* metric, meaning it measures the model's internal logic without needing a human "correct answer" to compare against.

### ROUGE (Recall-Oriented Understudy for Gisting Evaluation)
Used primarily for **Text Summarization**.
*   **How it works:** It counts how many words in the model's summary also appear in a "reference" summary written by a human.
*   **Metric Focus:** It focuses on **Recall** (did we capture all the important points?).

### BLEU (Bilingual Evaluation Understudy)
Used primarily for **Machine Translation**.
*   **How it works:** It measures the overlap between a model's translation and a human's translation.
*   **Metric Focus:** It focuses on **Precision** (how accurate are the words we chose?).

---

## 2. Traditional ML Metrics (Recap)

### Classification (Discrete Categories)
*   **Accuracy:** Overall correctness. Useful only for balanced datasets.
*   **Precision:** "Of all the positives we predicted, how many were right?" (Avoids False Positives).
*   **Recall:** "Of all the actual positives that exist, how many did we find?" (Avoids False Negatives).
*   **F1-Score:** The harmonic mean of Precision and Recall. Best for imbalanced data.
*   **Confusion Matrix:** A table Layout showing True Positives (TP), False Positives (FP), True Negatives (TN), and False Negatives (FN).

### Regression (Predicting Numbers)
*   **RMSE (Root Mean Square Error):** Measures the average "distance" between the predicted number and the actual number. Penalizes large errors heavily.
*   **MAE (Mean Absolute Error):** Similar to RMSE but doesn't penalize large outliers as aggressively.

---

## 3. The "Confusion" vs. "Confidence" Comparison

| Goal | Metric | Logic |
| :--- | :--- | :--- |
| **Measure Uncertainty** | **Perplexity** | How many options did the model struggle to choose between? |
| **Measure Text Quality**| **ROUGE / BLEU** | How close is the output to a "perfect" human example? |
| **Measure Factual Accuracy** | **Logprobs** | What was the mathematical probability (0-1) of the chosen word? |

---

## 4. Exam Tips: Which Metric to Choose?

*   **Summarization/Captions?** Choose **ROUGE**.
*   **Translation?** Choose **BLEU**.
*   **Model "Guts"/Confidence?** Choose **Perplexity** or **Logprobs**.
*   **Cancer detection or Medical?** Choose **Recall** (You cannot afford to miss a positive).
*   **Email Spam filtering?** Choose **Precision** (You cannot afford to accidentally block a real email).

---
*Last Updated: Jan 2026*
