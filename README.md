# Awesome Synthetic Data [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources, papers, and methods for **Scalable**, **Verifiable**, and **Agentic** Synthetic Data generation.

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

## 📖 Introduction

With the "Data Wall" approaching for public web data, **Synthetic Data** has become the critical engine for scaling Large Language Models (LLMs).

This repository organizes synthetic data methodologies by **Training Stages**—covering the full lifecycle from Pre-training to SFT and RL. Within each stage, we dive deep into specific **Domains** (Math, Code, Agent), focusing on the unique synthesis schemes (Efficiency, Verification, Simulation) required for each.

**Scope & Highlights:**
- ✅ **Stage 1: Pre-training:** Synthesizing "Textbooks" and knowledge-dense corpora.
- ✅ **Stage 2: SFT (Instruction Tuning):** Generating complex instructions for **Math**, **Code**, and **Agents** via Evolution and Simulation.
- ✅ **Stage 3: RL (Alignment):** Fueling **RLVR** (Verifiable Rewards) and Preference Optimization with synthetic ground truths.

---

## 目录 (Table of Contents)

- [Awesome Synthetic Data](#awesome-synthetic-data)
  - [📖 Introduction](#-introduction)
  - [Phase 1: Pre-training (The Foundation)](#phase-1-pre-training-the-foundation)
    - [01. General & Domain Textbooks](#01-general--domain-textbooks)
  - [Phase 2: SFT (Supervised Fine-Tuning)](#phase-2-sft-supervised-fine-tuning)
    - [02. General Instruction Tuning](#02-general-instruction-tuning)
    - [03. Math & Reasoning SFT](#03-math--reasoning-sft)
    - [04. Code Generation SFT](#04-code-generation-sft)
    - [05. Agentic & Tool-Use SFT](#05-agentic--tool-use-sft)
  - [Phase 3: RL & Alignment (The Refinement)](#phase-3-rl--alignment-the-refinement)
    - [06. RLVR (Verifiable Rewards for Math/Code)](#06-rlvr-verifiable-rewards-for-mathcode)
    - [07. General Preference Alignment (RLHF)](#07-general-preference-alignment-rlhf)
  - [Extras](#extras)
    - [📊 Evaluation & Benchmarks](#-evaluation--benchmarks)
    - [📝 Tutorials & Insights](#-tutorials--insights)
  - [Citation](#citation)

---

## Phase 1: Pre-training (The Foundation)
*Synthesizing massive, knowledge-dense corpora to replace or augment Common Crawl.*

### [01. General & Domain Textbooks](./01_Pretraining/README.md)
* **Textbook Synthesis:** Using strong models to write structured, educational content (e.g., *Cosmopedia*).
* **Web Rephrasing:** "Translating" noisy web text into clean, high-value formats (e.g., *FineWeb*).
* **Code/Math Stack Synthesis:** Generating synthetic GitHub repos or math proofs for base model reasoning.

---

## Phase 2: SFT (Supervised Fine-Tuning)
*The core synthesis stage: Turning base models into capable instruction followers across domains.*

### [02. General Instruction Tuning](./02_SFT_General/README.md)
* **Seed Evolution:** Methodologies to evolve simple prompts into complex tasks (e.g., *WizardLM*).
* **Self-Instruct:** The classic pipeline of generation and filtering.
* **Diversity Promotion:** Ensuring semantic coverage of verbs and topics.

### [03. Math & Reasoning SFT](./03_SFT_Math/README.md)
* **Chain-of-Thought (CoT) Synthesis:** Generating step-by-step reasoning paths.
* **Backward Synthesis:** Generating questions from answers to ensure solvability.
* **Process Verification:** Using solvers to filter synthetic SFT data (e.g., *Math-Shepherd*).

### [04. Code Generation SFT](./04_SFT_Code/README.md)
* **Execution-Feedback Loops:** Generating code -> Executing -> Self-Correction -> Final SFT Data.
* **OSS-Instruct:** Mining and synthesizing instructions from open-source codebases.
* **Unit-Test Synthesis:** Generating pairs of (Problem, Solution, Test Cases).

### [05. Agentic & Tool-Use SFT](./05_SFT_Agent/README.md)
* **Environment Simulation:** Collecting trajectories from Agents interacting with Sandbox/OS (e.g., *AgentTrek*).
* **Trajectory Filtering:** Only keeping "Success" traces from exploration.
* **Multi-Agent Roleplay:** Synthesizing social interactions via multi-agent debate.

---

## Phase 3: RL & Alignment (The Refinement)
*Synthesizing signals (Rewards/Pairs) to further push model boundaries.*

### [06. RLVR (Verifiable Rewards for Math/Code)](./06_RL_Verifiable/README.md) <span style="color:red">**(System 2 Focus)**</span>
* **Outcome-Based Synthesis:** Generating problems with deterministic binary rewards for PPO/GRPO.
* **Process Supervision (PRM):** Synthesizing step-level correctness labels.
* **Self-Correction Trajectories:** Generating data specifically to train "Try-Fail-Fix" behaviors.

### [07. General Preference Alignment (RLHF)](./07_RL_General/README.md) <span style="color:red">**(System 1 Focus)**</span>
* **AI Feedback (RLAIF):** Synthesizing preferences (Chosen vs. Rejected) using Model-as-a-Judge.
* **Critique & Revision:** Synthesizing natural language feedback loops (e.g., *Constitutional AI*).
* **Pairwise Data Generation:** Creating synthetic DPO datasets from single responses.

---

## 📊 Evaluation & Benchmarks
*Comparisons of data efficiency, model performance, and synthesis costs.*

## 🛠️ Tools & Frameworks
*Libraries and codebases for generating synthetic data.*

- **Distilabel** (Argilla)
- **Nemotron** (NVIDIA)

## 📝 Tutorials & Insights
*Blog posts, twitter threads, and industry talks about data synthesis economics.*

---

## 🤝 Contributing

We welcome contributions! Please see the [Contribution Guidelines](CONTRIBUTING.md) for details. 

1. Fork the repo.
2. Add the paper/resource to the relevant section's `README.md`.
3. Format: `[Paper Name](Link) - Author et al. (Conf Year)`.
4. Submit a Pull Request.

## Citation

If you find this repository useful for your research, please cite our survey (Coming Soon):

```bibtex
@misc{awesome-synthetic-data,
  author = {Zhennan Shen},
  title = {Awesome Synthetic Data: A Survey of Methodologies},
  year = {2026},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{[https://github.com/5456es/awesome-synthetic-data](https://github.com/5456es/awesome-synthetic-data)}},
}
