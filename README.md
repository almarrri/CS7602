# Evaluating LLM Safety with an AI Feedback Loop

## Overview

This project evaluates how Large Language Models (LLMs) handle prompts of varying risk levels and whether an AI-based feedback loop can improve response safety and quality.

We compare multiple models:

* ChatGPT (OpenAI API)
* Claude (Anthropic API)
* K2Think (manual evaluation)

The system uses an automated LLM-based critic to:

1. Evaluate model responses
2. Score safety and helpfulness
3. Generate improved responses

---

## Problem Statement

LLMs must balance:

* Helpfulness
* Safety

However, models may:

* Provide unsafe details
* Over-refuse
* Mis-handle ambiguous prompts

This project evaluates whether an AI feedback loop improves performance or introduces degradation.

---

## Project Structure

data/ → dataset (llm_dataset.json)
notebooks/ → evaluation notebook
report/ → final IEEE report
README.md → this file

---

## Dataset

The dataset contains 36 prompts across 4 categories:

* Benign (safe queries)
* Sensitive (requires caution)
* Dangerous (should be refused)
* Ambiguous (dual-use intent)

Each prompt includes:

* category
* expected_action (answer / cautious / refuse)

---

## Methodology

Step 1 — Model Response
Each model generates a response for each prompt

Step 2 — AI Critic Evaluation
The critic evaluates:

* Safe
* Helpful
* Unsafe Details

Step 3 — Scoring
Responses are scored based on expected behavior

Step 4 — Feedback Loop
The critic generates an improved response, which is re-evaluated

---

## Results Summary

ChatGPT → 0.97 → 0.75 (−0.22)
Claude  → 0.72 → 0.72 (0.00)
K2Think → 1.00 (manual subset)

Key Insight:
The AI feedback loop is not universally beneficial. It caused over-correction in ChatGPT while Claude remained stable.

---

## How to Run

1. Install dependencies
   pip install openai anthropic pandas

2. Set API keys

from getpass import getpass
OPENAI_API_KEY = getpass("Enter OpenAI key:")
ANTHROPIC_API_KEY = getpass("Enter Claude key:")

3. Run evaluation notebook
   Open notebooks/evaluation.ipynb and run all cells

---

## Reproducing Results (Reduced Demo)

To run a quick demo:

* Use first 5–10 prompts
* Run ChatGPT evaluation
* Run critic
* Generate summary

---

## K2Think Note

K2Think was evaluated manually due to resource constraints.

The Hugging Face version requires ~40GB, making it infeasible for Colab.

---

## Limitations

* Small dataset (36 prompts)
* LLM-based critic may introduce bias
* K2Think evaluated on subset only

---

## Future Work

* Larger datasets
* Multiple critics
* Adaptive feedback loops
* Efficient deployment of large open-source models

---

## Author

Mohamed Almarri
