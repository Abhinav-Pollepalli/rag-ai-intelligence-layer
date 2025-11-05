# Evaluation Protocol (RAG vs Gemini)

## Objective
Assess factual accuracy, citation reliability, and grounded reasoning when answering questions from a single academic PDF.

This protocol evaluates systems only on their ability to extract and cite information from the provided document, not general world knowledge.

## Dataset / Source
- One academic PDF (technical topic)
- Questions require evidence from the document

## Task
For each question:
- Answer using the PDF as the primary source
- Cite exact passages
- If information is missing, explicitly state so

## Scoring Rubric

Each question is scored out of **50 points**
(5 categories × 10 points each)

| Category | Max Points | Description |
|---|---|---|
| **1. Factual Grounding** | 10 | All claims must be directly supported by document text |
| **2. Citation Accuracy** | 10 | Correct direct quotes with accurate page/section references and proper quote formatting |
| **3. Contextual Reasoning** | 10 | Clear chain from retrieved evidence → reasoning → final answer |
| **4. Answer Quality** | 10 | Accurate, precise, complete, and readable with no fluff |
| **5. Missing-Info Handling** | 10 | States **"Not found in document"** when evidence is absent before using external knowledge. External info must be clearly labeled |

### Deductions (per violation)

| Error | Deduction |
|---|---|
Minor citation formatting issue | -2 |
Missing page/section reference | -5 |
Quote slightly paraphrased instead of exact text | -3 to -5 |
Incorrect factual claim based on document | -5 to -10 |
Logical leap / unsupported inference | -5 to -10 |
Failed to acknowledge missing info | -10 |
External info unlabeled or sourced incorrectly | -10 |

### Hallucination Rule

Defined as:
- Fabricating facts not in the PDF
- Inventing citations or page refs
- Misrepresenting the document content


## Result Summary
- RAG system observed **zero hallucinations under this protocol**
- RAG scored **493/500** vs **470/500** for Gemini (see report for breakdown)

## Notes
- Results reflect this protocol and dataset
- Future evaluations planned across larger document sets


## Question Set
See: docs/eval_questions.md

## Source Document
See: https://arxiv.org/pdf/2510.26518

## Evaluation Environment 
Pipeline details are withheld to protect ongoing work.


