# Legal Contract RAG System

## Summary

This project is a precision-focused legal document analyst. It uses the Qwen2.5-7B-Instruct (Full Precision) to parse, index, and query legal agreements. It also features a built-in LLM-as-a-Judge evaluation pipeline to continuously verify retrieval accuracy and factual consistency.

## Technical Stack & Hardware Requirements

- **Model:** Qwen/Qwen2.5-7B-Instruct (Full Precision)
- **Hardware:** Requires a GPU with 16GB-20GB of VRAM to support the full 7B model at high precision.
- **Storage:** FAISS Vector Database
- **Processing:** Parallel ingestion
- **Logic:** Multi-token filtering for source isolation

## Key Capabilities

- **Multi-Language:** Processes English, Arabic, Spanish, etc.. natively.
- **Verification:** Always provides the exact quote from the source document.
- **Precision:** Uses filename-matching rules to prevent context contamination.
- **Automated Evaluation:** Generates highly specific synthetic Q&A pairs grounded in single document chunks, then uses an LLM-as-a-Judge to grade the RAG pipeline's factual accuracy.

## Operating Steps

1. Start the server and upload numbered PDFs to the `/ingest` endpoint.
2. Submit specific queries (e.g., 'What is the rate in Contract 5?') to ensure the system applies correct filters.
3. Navigate to the **Evaluation** tab in the Gradio UI to run synthetic QA testing and view performance statistics.
