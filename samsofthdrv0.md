# Samsoft A/B Gemini 2HT – Gemini 3.0 Pro (ECPT Checkpoint — TESTED)

**Experimental A/B Evaluation Gem for Gemini-Class Models**

> Version: 1.1 (ECPT Tested)  
> Author: Flames Co Labs / Samsoft Interactive  
> License: GPL-3.0-or-later  

---

## 🧠 Overview
This document defines the **A/B testing harness** for evaluating the *Gemini 3.0 Pro (ECPT Checkpoint — TESTED)* build, a refined yet slightly “nerfed” iteration of the 2HT multimodal reasoning series.  
Compared against the legacy *Gemini 2.5 Pro* baseline, this checkpoint shows **~10 % lower composite fidelity** but remains **strong in UI, language, and aesthetic synthesis**.  

---

## ⚙️ Architecture

| Module | Purpose | Example |
|:--------|:---------|:---------|
| `ab_runner.py` | Orchestrates model calls and logs results | `python ab_runner.py --prompt test_ui.json` |
| `prompt_bank/` | Stores structured test prompts | `gameboy_gui.prompt`, `melee_trophy.prompt`, `yoshi_trophy.prompt` |
| `metrics.py` | Evaluates structural + semantic + aesthetic similarity | BLEU, AST-diff, color-palette coherence |
| `reporter.py` | Generates Markdown summaries of A/B results | `reports/2025-10-A-B-summary.md` |

---

## 🔬 Test Design
- **A-Path** → Gemini 2.5 Pro baseline  
- **B-Path** → Gemini 3.0 Pro (ECPT Checkpoint — TESTED)  
- **Metric** → Structural + Aesthetic + Functional score (out of 10)  
- **Observation** → “ECPT nerf” yields ≈ –10 % total score drop, but maintains consistency and creativity.

```python
# Example test schema
{
  "test_id": "UI-GB-600x400",
  "prompt": "Recreate Game Boy GUI using Tkinter...",
  "expected_features": ["color fidelity", "3D relief", "pixel grid"],
  "weights": {"structure": 0.3, "aesthetic": 0.4, "readability": 0.3}
}
