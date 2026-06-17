![Python](https://img.shields.io/badge/Python-3.10-blue)
![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-yellow)
![Research](https://img.shields.io/badge/Research-Published-success)

# Faithful Text Summarization

## Overview

This project explores abstractive text summarization using state-of-the-art transformer models and evaluates the faithfulness of generated summaries. The study compares summarization performance across the CNN/DailyMail and XSum datasets while assessing factual consistency using multiple evaluation metrics.

The primary objective is to investigate whether generated summaries accurately represent the source content and to identify potential hallucinations introduced by neural summarization models.

---

## Objectives

- Generate abstractive summaries using transformer-based models.
- Evaluate summary quality using standard NLP metrics.
- Measure factual consistency and faithfulness.
- Analyze hallucination tendencies in generated summaries.
- Compare performance across multiple benchmark datasets.

---

## Datasets

### CNN/DailyMail
A large-scale news summarization dataset containing news articles paired with human-written summaries.

### XSum
A highly abstractive summarization dataset where each article is summarized using a single concise sentence.

---

## Model

### BART (Bidirectional and Auto-Regressive Transformers)

Model Used:

text facebook/bart-large-cnn 

BART combines the strengths of:
- Bidirectional encoding (similar to BERT)
- Autoregressive decoding (similar to GPT)

It is widely used for abstractive summarization tasks and serves as the primary model in this project.

---

## Methodology

### 1. Data Preparation

- Load benchmark datasets.
- Preprocess article and summary text.
- Select evaluation samples.

### 2. Summary Generation

- Generate abstractive summaries using BART.
- Apply beam search decoding.
- Store generated summaries for evaluation.

### 3. Evaluation

Generated summaries are evaluated using:

#### ROUGE

Measures overlap between generated and reference summaries.

Metrics:
- ROUGE-1
- ROUGE-2
- ROUGE-L

#### BERTScore

Uses contextual embeddings to evaluate semantic similarity between generated and reference summaries.

Advantages:
- Captures meaning beyond lexical overlap.
- More robust than traditional n-gram metrics.

#### NLI-Based Faithfulness Assessment

Natural Language Inference (NLI) is used to evaluate factual consistency.

Model:

text roberta-large-mnli 

Possible outcomes:
- Entailment
- Neutral
- Contradiction

This helps detect potential hallucinations in generated summaries.

---

## Project Workflow

text Dataset    ↓ Preprocessing    ↓ BART Summarization    ↓ Generated Summary    ↓ ROUGE Evaluation    ↓ BERTScore Evaluation    ↓ NLI Faithfulness Assessment    ↓ Result Analysis 

---

## Technologies Used

- Python
- Google Colab
- Hugging Face Transformers
- PyTorch
- Datasets Library
- Evaluate
- BERTScore
- ROUGE
- RoBERTa-MNLI
- Pandas
- NumPy
- Matplotlib

---

## Repository Structure

text faithful-text-summarization/ │ ├── faithful_text_summarization.ipynb ├── README.md ├── requirements.txt └── results/ 

---

## Results

The project evaluates:

- Summary quality
- Semantic similarity
- Factual consistency
- Hallucination detection

Key findings include:

- CNN/DailyMail summaries generally achieve higher ROUGE scores.
- XSum is more challenging due to its highly abstractive nature.
- Faithfulness evaluation reveals cases where summaries introduce unsupported information.
- NLI-based analysis helps identify contradictions and hallucinations.

---

## Applications

- News summarization
- Document intelligence
- AI-assisted content generation
- Information retrieval
- Fact-aware summarization systems
- Trustworthy Generative AI

---

## Future Work

- Fine-tune BART on domain-specific datasets.
- Compare with T5 and PEGASUS models.
- Implement advanced hallucination detection methods.
- Explore explainable AI techniques for summarization evaluation.
- Develop a real-time summarization web application.

---

## Author

Devasish Viswanadh Kolla

B.Tech Computer Science and Engineering  
SRM University AP

Areas of Interest:
- Artificial Intelligence
- Natural Language Processing
- Cybersecurity
- Explainable AI
- Generative AI

---
## Related Innovation and Patent Work

This project aligns with ongoing research and innovation efforts in trustworthy Generative AI. The evaluation framework developed in this study contributes to the broader challenge of detecting factual inconsistencies and hallucinations in AI-generated content.

### Patent Concept

System and Method for Detecting Hallucinated Information in AI-Generated Summaries Using Multi-Stage Verification Architecture

The proposed architecture focuses on improving the reliability of AI-generated summaries through:

- Multi-stage verification pipelines
- Natural Language Inference (NLI)-based fact checking
- Semantic consistency analysis
- Contradiction detection mechanisms
- Confidence-based hallucination scoring
- Automated summary validation workflows

The concepts explored in this repository provide foundational insights into summary faithfulness assessment and support future development of trustworthy AI systems for high-stakes applications such as finance, healthcare, legal documentation, and enterprise knowledge management.

Status: Patent Draft Under Development
------
## License

This project is intended for academic, educational, and research purposes.
