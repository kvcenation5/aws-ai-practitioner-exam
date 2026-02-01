# Security, Compliance, and Governance for AI

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

Building AI solutions requires more than just performance; it requires a robust framework for security, data privacy, and regulatory compliance. This section covers the "Safety & Trust" pillar of AI development on AWS, moving from high-level strategy to technical implementation.

---

## 🏛️ 1. Core Functions: Security, Governance, & Compliance

While they overlap, these three functions have distinct primary goals in an AI organization.

| Function | Primary Goal | Focus Area |
| :--- | :--- | :--- |
| **Security** | Ensure **Confidentiality, Integrity, and Availability** (CIA) of data and infrastructure. | Cyber defenses, infrastructure protection, threat prevention. |
| **Governance** | Ensure the organization can **add value and manage risk** in business operations. | Roles, responsibilities, decision-making boards, oversight. |
| **Compliance** | Ensure **normative adherence** to requirements and legal standards. | HIPAA, GDPR, SOC2, industry-specific audits. |

!!! tip "Exam Tip"
    These are often considered "most important requirements"—the things that must not be sacrificed during product development or delivery.

---

## 🛡️ 2. Defense in Depth for AI

The **Defense in Depth** paradigm uses multiple redundant defenses to protect your AWS accounts, workloads, and data. If one control fails, other layers still isolate the threat.

### Why apply it to Generative AI?
*   **Layered Controls:** Mitigates common risks (like prompt injection or data leakage) by stacking security checks.
*   **Familiar Tools:** Allows teams to govern AI workloads using standard AWS security tools.
*   **Resiliency:** Helps prevent, detect, respond to, and recover from security events.

### The 7 Layers of Defense (Outermost to Innermost)
1.  **Network** (e.g., VPC, PrivateLink)
2.  **Identity & Access** (e.g., IAM Roles, Least Privilege)
3.  **Compute** (e.g., Secure Instances, Enclaves)
4.  **Application** (e.g., Bedrock Guardrails, SageMaker Models)
5.  **Data** (e.g., Macie PII Redaction, KMS Encryption)
6.  **Human** (e.g., Governance Boards, HITL review)
7.  **Physical** (Handled by AWS Data Centers)

---

## ⚖️ 3. Establishing a Governance Framework

A high-level governance strategy ensures the responsible deployment of AI technologies throughout their lifecycle.

### Steps to Build a Governance Framework:
1.  **Establish an AI Governance Board/Committee:**
    *   A cross-functional team including **legal, compliance, data privacy experts, and AI developers**.
2.  **Define Roles and Responsibilities:**
    *   Clearly outline who is responsible for oversight, policy-making, risk assessment, and final decision-making.
3.  **Implement Policies and Procedures:**
    *   Develop comprehensive rules addressing the **entire AI lifecycle**—from data collection/cleaning to final model monitoring.

---

## 📂 4. Data Governance Strategies

### Data Lineage & Provenance
*   **Definition:** Tracking data from its origin (source) through every transformation to the final model.
*   **Source Citation:** Documenting exactly where data came from to ensure licensing compliance and validity.
*   **Metadata Management:** Tagging data with information about its sensitivity, owner, and expiration date.

### Secure Data Engineering Best Practices
*   **Anonymization/Masking:** Removing Personally Identifiable Information (PII) before training.
*   **Encryption at Rest & In Transit:** Using **AWS KMS** to encrypt data in S3 and TLS for data in motion.
*   **Macie Integration:** Using **Amazon Macie** to automatically discover and protect PII stored in Amazon S3.

---

## 🛠️ 5. AWS Services for Security & Governance

| Service | Category | Role in AI Governance |
| :--- | :--- | :--- |
| **Amazon Bedrock Guardrails** | Security | Filter toxic content and PII in real-time. |
| **AWS IAM** | Identity | Enforce "Least Privilege" access to models and data. |
| **AWS PrivateLink** | Network | Keep AI traffic within the AWS network (avoiding public internet). |
| **AWS KMS** | Data Security | Manage encryption keys for models and datasets. |
| **AWS Artifact** | Compliance | Download compliance reports (HIPAA, ISO) to verify infrastructure. |
| **AWS CloudTrail** | Auditing | Record every API call made to SageMaker/Bedrock for forensic audits. |
| **SageMaker Model Cards** | Documentation | Standardized documentation for model risks and intended use. |

---

## ⚖️ 6. Implementation Strategies

1.  **Establish KPIs:** Link security and compliance metrics to business value early.
2.  **Human-in-the-Loop (HITL):** Use **Amazon SageMaker Ground Truth** or **A2I** for critical oversight.
3.  **Continuous Monitoring:** Use **SageMaker Model Monitor** to detect drift or bias in production.
4.  **Experimentation:** Use **A/B Testing** or **Canary Deployments** to validate model variants safely.

---
*Last Updated: Jan 2026*
