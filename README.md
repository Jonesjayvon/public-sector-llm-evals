# Public Sector LLM Evaluation Benchmark & Dataset

[![Eval Focus](https://img.shields.io/badge/Eval-Accuracy%20%26%20Policy%20Safety-blue)](#)
[![Domain](https://img.shields.io/badge/Domain-Public%20Sector%20%2F%20Defense-green)](#)
[![Format](https://img.shields.io/badge/Format-JSON%20%2F%20Markdown-orange)](#)

## 📌 Overview

Evaluating Large Language Models (LLMs) for enterprise and public sector use requires testing far beyond general knowledge benchmarks (e.g., MMLU or GSM8k). In federal and national security environments, models must adhere strictly to regulatory frameworks (such as the Federal Acquisition Regulation - FAR), maintain high factual precision without hallucination, and resist domain-specific adversarial prompt injection.

This repository contains a curated **evals dataset and testing methodology framework** designed to test LLM capabilities on:
1. **Regulatory Accuracy & QA:** Precise interpretation of complex government acquisition policies.
2. **Helpfulness vs. Harmlessness Tradeoffs:** Navigating sensitive, non-classified government operational queries.
3. **Hallucination & Groundedness Scoring:** Verifying model adherence to provided reference texts.

---

## 🧪 Evaluation Methodology

Evaluations in this framework utilize a **3-Tier Grading Scale** to score model outputs:

```mermaid
flowchart TD
    A["Prompt Input"] --> B["LLM Inference Execution"]
    B --> C["Evaluation Harness / Judge"]
    
    C --> D["Accuracy Score<br/>(0.0 - 1.0)<br/>• Correct regulatory cite<br/>• Factually sound"]
    C --> E["Groundedness Score<br/>(0.0 - 1.0)<br/>• 100% sourced from context<br/>• Zero hallucinated facts"]
    C --> F["Safety & Policy<br/>(Pass / Fail)<br/>• Zero unauthorized disclosure<br/>• Robust prompt injection defense"]

    style A fill:#e3f2fd,stroke:#1565c0,stroke-width:1px
    style B fill:#fff3e0,stroke:#e65100,stroke-width:1.5px
    style C fill:#f3e5f5,stroke:#7b1fa2,stroke-width:1.5px
    style D fill:#e8f5e9,stroke:#2e7d32,stroke-width:1px
    style E fill:#e8f5e9,stroke:#2e7d32,stroke-width:1px
    style F fill:#ffebee,stroke:#c62828,stroke-width:1px
