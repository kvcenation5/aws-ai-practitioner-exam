# Security, Compliance, and Governance for AI

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Building AI solutions requires more than just performance; it requires a robust framework for security, data privacy, and regulatory compliance. This section covers the "Safety & Trust" pillar of AI development on AWS.

---

## 🏛️ 1. Governance and Compliance Requirements

Governance in AI refers to the set of rules, practices, and processes by which an AI system is directed and controlled.

### Key Considerations:
*   **Regulatory Compliance:** Meeting industry-specific standards like **HIPAA** (Healthcare), **GDPR** (Privacy), or **SOC2** (Security).
*   **Model Inventory:** Keeping a record of every model, its version, and its purpose (using **SageMaker Model Registry**).
*   **Auditability:** The ability to trace back a model's prediction to the specific dataset and training code used (Lineage).
*   **Transparency:** Explaining how a model makes decisions (using **SageMaker Clarify**).

---

## 📂 2. Data Governance Strategies

Data is the lifeblood of AI. Governing this data ensures it is high-quality, secure, and used ethically.

### Data Lineage & Provenance
*   **Definition:** Tracking data from its origin (source) through every transformation to the final model.
*   **Source Citation:** Documenting exactly where data came from to ensure licensing compliance and validity.
*   **Metadata Management:** Tagging data with information about its sensitivity, owner, and expiration date.

### Secure Data Engineering Best Practices
*   **Anonymization/Masking:** Removing Personally Identifiable Information (PII) before training.
*   **Encryption at Rest & In Transit:** Using **AWS KMS** to encrypt data in S3 and while it moves between services.
*   **Least Privilege Access:** Using **IAM Roles** to ensure only authorized users can touch sensitive training sets.

---

## 🔒 3. Securing AI Systems on AWS

Security is a "Shared Responsibility." AWS secures the infrastructure, while you secure the code, model, and data.

### Security Concerns for AI:
*   **Prompt Injection:** Unauthorized prompts designed to bypass safety filters.
*   **Data Poisoning:** Maliciously altering training data to create bias or backdoors.
*   **Model Theft:** Unauthorized access to model artifacts.

### AWS Services for Security & Privacy:
*   **Amazon Bedrock Guardrails:** The primary tool for preventing toxic content, filtering PII, and enforcing safety policies in GenAI.
*   **Amazon Macie:** Automatically discovers and protects sensitive data (like PII) in Amazon S3.
*   **AWS PrivateLink:** Ensures your AI traffic stays within the AWS network and doesn't traverse the public internet.
*   **IAM (Identity & Access Management):** The "Gatekeeper" for all AWS AI services.

---

## 🛠️ 4. AWS Services for Governance Controls

| Service | Role in AI Governance |
| :--- | :--- |
| **AWS Artifact** | Your central resource for **compliance reports** (ISO, PCI, etc.). Useful for proving AWS infrastructure is secure. |
| **AWS Audit Manager** | Helps you continuously audit your AWS usage to simplify how you assess risk and compliance. |
| **AWS CloudTrail** | Logs every API call made to SageMaker or Bedrock. Vital for **forensic audits**. |
| **AWS Config** | Monitors and records your AWS resource configurations to ensure they meet compliance "rules." |
| **SageMaker Model Cards** | Provides a standardized way to document model information (training details, intended use, risk ratings). |

---

## ⚖️ 5. Implementing Governance Strategies

1.  **Establish KPIs:** Define what "Success" and "Safety" look like early (Business Goal Identification).
2.  **Human-in-the-Loop (HITL):** Use **Amazon SageMaker Ground Truth** or **A2I** for human review of sensitive model outputs.
3.  **Continuous Monitoring:** Use **SageMaker Model Monitor** to detect drift or bias in production.
4.  **Automated Guardrails:** Implement real-time filtering to catch prompt misuse before it reaches the user.

---
*Last Updated: Jan 2026*
