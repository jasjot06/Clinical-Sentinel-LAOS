# The Clinical Sentinel: LAOS-Inspired Medical AI Pipeline 🩺🤖

A fully localized, privacy-compliant Clinical Decision Support System (CDSS) that synthesizes medical consultation audio into structured Electronic Health Record (EHR) JSON notes. 

## 🚀 Key Features
* **Custom ASR Optimization:** Fine-tuned OpenAI's Whisper on synthetic clinical audio to handle complex medical terminology, reducing Word Error Rate (WER) from 12.6% to 4.0%.
* **Precision RAG Architecture:** Utilizes a local ChromaDB for semantic search of verified medical guidelines, combined with CPU-offloaded Cross-Encoder reranking to bypass GPU deadlocks.
* **Retrieval-Augmented Fine-Tuning (RAFT):** Llama-3 (8B) adapted via LoRA to eliminate cross-domain hallucinations (Domain Bleed).
* **Deterministic Output:** Generates structured JSON notes with diagnostic impressions and actionable treatment plans.

## 📊 Performance Metrics
Evaluated against 57 complex, multi-domain General Practice consultations from the PriMock57 dataset:
* **BERTScore (F1):** 0.8335
* **ROUGE-1:** 0.3586
* **Word Error Rate (WER):** Reduced from 12.6% to 4.0%

## 📦 Model Weights (LoRA Adapters)
Due to GitHub's file size limits, the fine-tuned Llama-3 LoRA adapters (RAFT) and the optimized Whisper weights are hosted externally. 

📥 **[Download the Fine-Tuned Model Weights (.zip) Here](https://drive.google.com/file/d/18k02mKVT5YGJs7S2tDT_iIpJdc7ZChqI/view?usp=sharing)**

*Extract this zip file into the `/models/lora_adapters/` directory before running the pipeline locally.*

## 🛠️ Tech Stack
* **Models:** Llama-3 (8B), OpenAI Whisper, BAAI/bge-reranker-base
* **Frameworks/Libraries:** PyTorch, HuggingFace Transformers, PEFT/LoRA, LangChain
* **Vector Database:** ChromaDB

## 💻 Getting Started
1. Clone the repository:
   ```bash
   git clone [https://github.com/jasjot06/Clinical-Sentinel-LAOS.git](https://github.com/jasjot06/Clinical-Sentinel-LAOS.git)
   cd Clinical-Sentinel-LAOS
