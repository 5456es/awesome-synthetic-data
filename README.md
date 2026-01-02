# Awesome Synthetic Data [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources, papers, and methods for **Scalable**, **Verifiable**, and **Agentic** Synthetic Data generation.

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

## 📖 Introduction

With the "Data Wall" approaching for public web data, **Synthetic Data** has become the critical frontier for scaling Large Language Models (LLMs) and Agents.

This repository tracks the evolution of synthetic data from simple instruction following (SFT) to complex **Reasoning**, **Code Execution**, and **Agentic Interaction**. We focus particularly on methods that leverage **Efficiency** (Small Models + Compute), **Verification** (Rule/Environment feedback), and **Reinforcement Learning** (RL) to break the limits of human-labeled data.

**Scope:**
- ✅ **Generation Pipelines:** How to synthesize data (Self-Instruct, Evolution, Simulation).
- ✅ **Verification & Filtering:** How to ensure quality (Execution, Reward Models).
- ✅ **RLVR & Feedback:** Leveraging ground-truth signals (Math/Code) vs. preference signals (Chat).

---

## 目录 (Table of Contents)

- [Awesome Synthetic Data](#awesome-synthetic-data)
  - [📖 Introduction](#-introduction)
  - [01. Pretraining Scaling (Universal Corpus)](#01-pretraining-scaling-universal-corpus)
  - [02. Reasoning & Math (Logic & CoT)](#02-reasoning--math-logic--cot)
  - [03. Code Engineering (Generation & Execution)](#03-code-engineering-generation--execution)
  - [04. Agentic Interaction (Trajectory & Env)](#04-agentic-interaction-trajectory--env)
  - [05. General SFT (Instruction Tuning)](#05-general-sft-instruction-tuning)
  - [06. RLVR & Verifiable Reinforcement](#06-rlvr--verifiable-reinforcement) <span style="color:red">**(New & Hot)**</span>
  - [07. Preference Alignment (RLHF & RLAIF)](#07-preference-alignment-rlhf--rlaif)
  - [📊 Evaluation & Benchmarks](#-evaluation--benchmarks)
  - [🛠️ Tools & Frameworks](#️-tools--frameworks)
  - [📝 Tutorials & Insights](#-tutorials--insights)
  - [🤝 Contributing](#-contributing)
  - [Citation](#citation)

---

## 01. Pretraining Scaling (Universal Corpus)
*Focus: Methodologies for synthesizing "Textbook Quality" data, rephrasing web noise, and knowledge distillation for base model pre-training.*

- [**Model-Based Synthesis**](./01_Pretraining/README.md#model-based)
  > Generating new knowledge or textbooks from scratch (e.g., *Cosmopedia*, *Phi-1.5*).
- [**Rephrasing & Augmentation**](./01_Pretraining/README.md#rephrasing)
  > Rewriting low-quality web data into high-quality formats (e.g., *FineWeb-Edu*, *RefinedWeb*).
- [**Synthetic-Real Mixing Strategies**](./01_Pretraining/README.md#mixing-strategies)
  > Research on the optimal ratio of synthetic vs. real data and scaling laws.

## 02. Reasoning & Math (Logic & CoT)
*Focus: Synthesizing step-by-step reasoning (CoT), formal proofs, and logic puzzles using verification mechanisms.*

- [**Prompt-Driven CoT**](./02_Reasoning_Math/README.md#prompt-driven)
  > Using strong models to generate reasoning chains via specialized prompting (e.g., *WizardMath*).
- [**Verification-Based (Process Reward)**](./02_Reasoning_Math/README.md#verification-based)
  > Filtering data via Python scripts, solvers, or Reward Models (e.g., *Math-Shepherd*, *Let's Verify Step by Step*).
- [**Backward Synthesis**](./02_Reasoning_Math/README.md#backward-synthesis)
  > Generating questions based on known answers to ensure solvability and control difficulty.

## 03. Code Engineering (Generation & Execution)
*Focus: Leveraging compilers, interpreters, and unit tests to synthesize zero-hallucination code data.*

- [**Self-Instruct (Static)**](./03_Code_Engineering/README.md#self-instruct)
  > Standard instruction generation for coding tasks (e.g., *CodeAlpaca*).
- [**Execution-Feedback Loop**](./03_Code_Engineering/README.md#execution-feedback)
  > Iterative synthesis where execution errors (stderr) drive self-correction (e.g., *Exec-Instruct*).
- [**Unit Test & Debugging Synthesis**](./03_Code_Engineering/README.md#unit-test-synthesis)
  > Synthesizing test cases first to verify generated code (e.g., *CodeT*).

## 04. Agentic Interaction (Trajectory & Env)
*Focus: Synthesizing trajectories for tool use, planning, and environment interaction (Web/OS).*

- [**Environment-Based Simulation**](./04_Agentic_Interaction/README.md#environment-simulation)
  > Recording successful trajectories in real sandboxes like OS or Web (e.g., *AgentTrek*, *WebArena*).
- [**Model-Simulated Interaction**](./04_Agentic_Interaction/README.md#model-simulated)
  > Using models to simulate user-agent dialogues and tool outputs (e.g., *ToolAlpaca*).
- [**Multi-Agent Roleplay**](./04_Agentic_Interaction/README.md#multi-agent)
  > Synthesizing social or collaborative data via multi-agent debate (e.g., *CAMEL*, *ChatDev*).

## 05. General SFT (Instruction Tuning)
*Focus: Enhancing diversity, complexity, and instruction-following capabilities for general chat.*

- [**Seed Evolution (Depth/Breadth)**](./05_General_SFT/README.md#seed-evolution)
  > Evolving simple instructions into complex tasks (e.g., *WizardLM*).
- [**Cloning & Distillation**](./05_General_SFT/README.md#cloning)
  > Recovering skills from proprietary models (e.g., *Alpaca*, *Vicuna*).
- [**Diversity-Driven Synthesis**](./05_General_SFT/README.md#diversity-driven)
  > Ensuring coverage of rare tasks and verbs.

## 06. RLVR & Verifiable Reinforcement
*Focus: "System 2" RL using Ground Truth or Rule-Based Verifiers (The DeepSeek-R1 / o1 paradigm).*

- [**Outcome-based Reinforcement**](./06_RLVR_Verifiable/README.md#outcome-based)
  > Utilizing compilers (Code) or answers (Math) as binary reward signals (e.g., *DeepSeek-R1* methods).
- [**Process Supervision (PRM)**](./06_RLVR_Verifiable/README.md#process-supervision)
  > Synthesizing step-by-step reward signals to guide reasoning search.
- [**Self-Correction Loops**](./06_RLVR_Verifiable/README.md#self-correction)
  > Training models to critique and refine their own outputs based on verification failures.

## 07. Preference Alignment (RLHF & RLAIF)
*Focus: "System 1" RL using Fuzzy Human/Model Preferences (Chosen vs. Rejected).*

- [**AI Feedback (RLAIF)**](./07_Preference_Alignment/README.md#ai-feedback)
  > Using models as judges to label preferences (e.g., *UltraFeedback*, *Starling*).
- [**Critique & Revision**](./07_Preference_Alignment/README.md#critique-revise)
  > Synthesizing natural language feedback for training self-refinement (e.g., *Constitutional AI*).
- [**Pairwise Data Synthesis**](./07_Preference_Alignment/README.md#pairwise-synthesis)
  > Generating high-quality DPO/PPO pairs from single responses.

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
