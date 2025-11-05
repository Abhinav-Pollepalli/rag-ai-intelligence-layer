## ⚠️ Note: This repository contains evaluation artifacts and documentation only. 
## ⚠️ Gemini is a Google product. This work is independent and not affiliated with or endorsed by Google.
The core implementation and prompts are proprietary and not included.

# RAG AI Intelligence Layer

- Evidence-grounded answers from PDFs with citation transparency.  
- This repo publishes documentation and evaluation artifacts. Core implementation is private.

## About
A research-grade Retrieval-Augmented Generation (RAG) system that turns academic PDFs into an interactive assistant. It combines parsing, semantic retrieval, and LLM reasoning to extract, analyze, and summarize technical documents with **strict citation requirements**.

---

### Modes

| Mode | Description |
|------|-------------|
| **Research** | Deep reasoning & citations (most accurate) |
| **Founder** | Balanced smart + fast |
| **Turbo** | Speed-first for quick tasks |


---

### Demo

Demo recordings for each mode are available in the `demo/` directory:
- **Research Mode:** Demonstrates deep reasoning and document citation.
- **Founder Mode:** Shows balanced strategic reasoning and fast response.
- **Turbo Mode:** Highlights speed-focused answers for quick tasks.

---

## Features
- **Hybrid PDF parsing:** text extraction + OCR fallback for scanned docs  
- **Intent-aware reasoning:** routes to Q&A, notes summary, conversation summary, or general Q (no context)  
- **Adaptive summarization:** merges partials into a coherent output  
- **Citation transparency:** exact quotes + page/section references. “not found in document” fallback  
- **Interactive UI prototype:** Gradio-based upload & querying

---

## Architecture (conceptual)
```
User input (PDF and/or question)
            ↓
PDF text extraction (+ OCR if needed)
            ↓
Sentence tokenization and token-aware chunking
            ↓
Embedding + vector storage
            ↓
Initial recall → re-ranking
            ↓
Context assembly + evidence-structured prompting
            ↓
LLM response with direct quotes and a “not found in document” fallback
```

*Implementation details (models, stores, thresholds) are intentionally omitted to protect IP.*

---
## Evaluation Result
In a controlled, document-grounded evaluation with strict citation rules, the RAG system scored 493/500 (zero hallucinations under this protocol) vs 470/500 for Gemini Pro.

- **Protocol:** `docs/eval_protocol.md`  
- **Questions:** `docs/eval_questions.md`  
- **Full report:** `docs/research_evaluation.md` and `docs/research_evaluation.pdf`  
- **Source PDF used:** https://arxiv.org/pdf/2510.26518

*Pipeline details are withheld. The evaluation is reproducible given the PDF, questions, and rubric.*

---

## What’s included / What’s omitted
**Included (public)**  
- Architecture overview (conceptual)  
- Evaluation protocol, questions, results, summary  
- Source paper used for the benchmark

**Omitted (proprietary)**  
- Prompting logic and templates  
- Retrieval/chunking parameters and heuristics  
- Reranking configuration and thresholds  
- Full application code and evaluation scripts

---
Licensing: Evaluation artifacts are provided under CC-BY-NC-4.0. 
The RAG engine implementation remains proprietary.