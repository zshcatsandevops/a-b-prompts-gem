# Samsoft A/B Gemini 3.0 Beta

**Experimental A/B Evaluation Gem for Gemini-Class Models**



> Version: 1.0 (Prototype)

> Author: Flames Co Labs / Samsoft Interactive

> License: GPL-3.0-or-later



---



## 🧠 Overview

This document defines the **A/B testing harness** for evaluating *Gemini 3.0 Beta*-class multimodal reasoning models against legacy *Gemini 2.5 Pro* baselines.  

The gem allows controlled comparison of **UI generation, code synthesis, and creative reasoning fidelity**.



---



## ⚙️ Architecture

| Module | Purpose | Example |

|---------|----------|----------|

| `ab_runner.py` | Orchestrates model calls and logs results | `python ab_runner.py --prompt test_ui.json` |

| `prompt_bank/` | Stores structured test prompts | `gameboy_gui.prompt`, `melee_trophy.prompt` |

| `metrics.py` | Evaluates structural and semantic similarity | BLEU, AST-diff, color palette matching |

| `reporter.py` | Generates Markdown summary of A/B results | `reports/2025-10-A-B-summary.md` |



---



## 🔬 Test Design

- **A-Path** → Gemini 2.5 Pro baseline output  

- **B-Path** → Gemini 3.0 Beta output  

- **Metric** → Structural + Aesthetic + Functional score out of 10  



```python

# Example test schema

{

  "test_id": "UI-GB-600x400",

  "prompt": "Recreate Game Boy GUI using Tkinter...",

  "expected_features": ["color fidelity", "3D relief", "pixel grid"],

  "weights": {"structure": 0.3, "aesthetic": 0.4, "readability": 0.3}

}
