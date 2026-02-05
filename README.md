# 🇧🇩 Bangla to English Translation Benchmark: SOTA Model Comparison

This project benchmarks State-of-the-Art (SOTA) Neural Machine Translation (NMT) models and Large Language Models (LLMs) on a custom dataset of 2,000 Bangla-English pairs. It evaluates performance using advanced metrics (BLEU, ROUGE, METEOR, BERTScore) to distinguish between structural accuracy (NMT) and semantic fluency (LLMs).

## 🚀 Project Overview

Translating low-resource languages like Bangla often requires a trade-off between **Local Expert Models** (trained specifically on Bangla), **Massive Multilingual Models** (Meta/Google), and **Generative LLMs** (Reasoning models). This repository implements a unified pipeline to compare these three distinct architectures side-by-side.

**Key Features:**

- **Multi-Model Inference:** Runs NLLB (Meta), BanglaT5 (BUET), mBART-50 (Meta), and Qwen-2.5 (Alibaba) in a single pipeline.
- **Generative vs. NMT:** Compares traditional Encoder-Decoder models against modern Decoder-only LLMs.
- **Advanced Evaluation:** Goes beyond BLEU to include Semantic Similarity (BERTScore) and Recall-based metrics (ROUGE/METEOR).
- **Technical Fixes:** Includes custom scripts for **Bangla text normalization**, **tokenizer patching** for modern transformers, and **4-bit quantization** for LLMs.

## 📊 Models Evaluated

| Model                      | Type             | Provider      | Why we chose it?                                                                                                                |
| :------------------------- | :--------------- | :------------ | :------------------------------------------------------------------------------------------------------------------------------ |
| **NLLB-200 (Distilled)**   | Encoder-Decoder  | Meta AI       | The "Baseline" for high-speed multilingual translation.                                                                         |
| **BanglaT5**               | T5 (Seq2Seq)     | CSE BUET      | A "Local Expert" model trained specifically on Bangla corpus; excellent for grammatical structure.                              |
| **mBART-50 (Large)**       | Encoder-Decoder  | Meta AI       | A massive "Heavy-Duty" model known for stability and handling complex sentence structures.                                      |
| **Qwen-2.5-7B (Instruct)** | Decoder-only LLM | Alibaba Cloud | **SOTA Open-Source LLM.** Evaluates how well a generative "reasoning" model translates compared to translation-specific models. |

## 📂 Dataset

- **Source:** Custom dataset (`bn_en_pairs.csv`) containing ~2,000 parallel sentences.
- **Preprocessing:**
  - Removed metadata artifacts.
  - **Normalization:** Applied `csebuetnlp/normalizer` to standardize Bangla Unicode characters (critical for BanglaT5).
  - **Filtering:** Removed nulls and whitespace.

## 🛠️ Installation & Usage

### 1. Clone the Repository

```bash
git clone https://github.com/abir2010/Bangla-to-English-Translation-Benchmark-SOTA-Model-Comparison.git
```
