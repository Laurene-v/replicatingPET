# replicatingPET
This is the code used for the paper "A Looming Replication Crisis in Evaluating Behavior in Language Models? Evidence and Solutions", https://arxiv.org/abs/2409.20303 . It is used to easily replicate prompt engineering techniques on selected benchmarks, LLMs, and verification methodologies.

---

## Overview

This repository contains the code accompanying the paper  
**“A Looming Replication Crisis in Evaluating Behavior in Language Models? Evidence and Solutions.”**

It provides a **modular and extensible pipeline** for reproducing and extending the paper’s experiments —  
including prompt engineering techniques, model evaluation, and output verification.

The goal is to make it **easy to replicate and adapt**:
- Use your **own benchmarks** or datasets.  
- Plug in **different language models (LLMs)**.  
- Implement your **own verification methodologies**.  

---

## Pipeline Overview

The workflow is organized into **four modular steps**, each implemented as a Jupyter notebook:

| Step | Notebook | Purpose |
|------|-----------|----------|
| **1. Get processed benchmarks** | `STEP1_Get_processed_benchmarks.ipynb` | Clean and normalize raw benchmark data (fix punctuation, unify structure) to ensure consistency across experiments. |
| **2. Modify benchmarks (Prompt Engineering)** | `STEP2_get_PET_benchmarks.ipynb` | Apply prompt engineering techniques to benchmarks; e.g., add “think step-by-step” (Zero-Shot-CoT) or reframe questions using LLMs. The original, unprocessed questions are preserved to track changes. |
| **3. Generate model answers** | `STEP3_get_LLM_answers.ipynb` | Call the selected models (OpenAI, Hugging Face, or custom APIs) to obtain answers for all benchmark questions after prompt modifications. |
| **4. Classify and verify outputs** | `STEP4_outputclassification.ipynb` | Run automated evaluation and classification using either regex-based rules or LLM-as-a-judge techniques. |

Each step can be used independently or as part of the full evaluation pipeline.

---
