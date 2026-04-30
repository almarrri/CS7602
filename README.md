# Evaluating LLM Safety with an AI Feedback Loop

## Overview
This project evaluates how Large Language Models (LLMs) handle prompts of varying risk levels and whether an AI-based feedback loop can improve response safety and quality.

We compare multiple models:
- ChatGPT (OpenAI API)
- Claude (Anthropic API)
- K2Think (manual evaluation)

The system uses an automated **LLM-based critic** to:
1. Evaluate model responses
2. Score safety and helpfulness
3. Generate improved responses

---

## Problem Statement
LLMs must balance:
- **Helpfulness**
- **Safety**

However, models may:
- Provide unsafe details
- Over-refuse
- Mis-handle ambiguous prompts

This project evaluates whether an **AI feedback loop** improves performance or introduces degradation.

---

## Project Structure

