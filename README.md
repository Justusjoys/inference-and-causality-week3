# Session 5 and 6 — Inference and Causality

This repository contains the materials for **Week 3** of Inference and Causality course.  
- Slides: see [`slides/`](./slides/) folder  
- Notebooks: see [`notebooks/`](./notebooks/) folder 
---

## 📑 Sessions Outline
### Observation vs Intervention • Conditional Independence • Proxy Variables
### Counterfactuals • Randomized Controlled Trials (RCTs)


## Learning Objectives
By the end of this week, you will be able to:

- Distinguish between **seeing** and **doing** in causal inference.  
- Explain the meaning of **P(Y|X)** vs **P(Y|do(X))**.  
- Interpret causal structures like **chains**, **forks**, and **colliders** using simulation.  
- Identify **confounders** and understand how interventions break spurious links.  
- Use **proxy variables** to handle **unobserved confounding**.  
- Understand the intuition behind **Pearl’s do-calculus**.
- Explain the **counterfactual** concept.
- Recognize the logic behind **Randomized Controlled Trial (RCT)** and evaluate studies based on the study desing.

---

## Week 3 Structure

| Session | Topic |
|:--------|:------|
| **Session 5** | Observation vs Intervention | 
|  | Conditional Independence (Chain/Fork/Collider) | 
|  | Do-Calculus: History & Motivation | 
| **Session 6** | Counterfactuals and Randomized Controlled Trials (RCTs)  | |

---

## Session Notebook Materials

### [1_InferenceAndCausality_Week3_ObservationVsInterversion.ipynb](notebooks/1_InferenceAndCausality_Week3_ObservationVsInterversion.ipynb)
Hands-on simulation notebook illustrating:
- Pearl’s **firing squad** scenario  
- Computing `P(D | SA=0)` vs `P(D | do(SA=0))`  
- Visualizing how the captain’s order acts as a **confounder**  
- Connecting DAG reasoning with empirical simulation

---

### [notebooks/2_InferenceAndCausality_Week3_ConditionalIndependence.ipynb](notebooks/2_InferenceAndCausality_Week3_ConditionalIndependence.ipynb)
Interactive examples of:
- **Chain (A → B → C)** — conditioning *blocks* transmission  
- **Fork (A ← U → C)** — conditioning *removes* confounding  
- **Collider (A → B ← C)** — conditioning *creates* spurious dependence  
- Comparison of **marginal** vs **conditional** correlations with numeric output table

---

### [notebooks/3_InferenceAndCausality_Week3_ProxyData.ipynb](notebooks/3_InferenceAndCausality_Week3_ProxyData.ipynb)
Simulating **unobserved confounding** and **proxy adjustment**:
- `U` = true exposure (unobserved)  
- `X` = self-reported smoking (noisy)  
- `NL` = nicotine-level biomarker (accurate proxy)  
- Demonstrates:
  - Naive model: `Y ~ X` (biased)  
  - Proxy-adjusted: `Y ~ X + NL` (unbiased)  
  - Biomarker-only: `Y ~ NL` (close to true causal effect)

---

## Key Concepts

| Concept | Description |
|:--------|:-------------|
| **Seeing vs Doing** | Observation ≠ Intervention — only interventions cut incoming edges to the variable in a DAG. |
| **Confounding** | Occurs when a variable influences both X and Y, causing \( P(Y|X) \ne P(Y|do(X)) \). |
| **Conditional Independence** | Foundation for d-separation and back-door adjustment. |
| **Proxy Variable** | Observable stand-in for a hidden cause (e.g., biomarker for true exposure). |
| **Do-Calculus** | Pearl’s logical rules for transforming probabilistic expressions containing `do(·)` into purely observational ones. |

---

## Homework 
Please fill out exercised at the bottum of notebooks and push your changes on your forked repo.


---
## 🚀 Environment Setup

Before starting, please **fork this repository** and create a fresh Python virtual environment.  
All required libraries are listed in `requirements.txt`.

> ⚠️ If you encounter errors during `pip install`, try removing the version pinning for the failing package(s) in `requirements.txt`.  
> On Apple M1/M2 systems you may also need to install additional system packages (the “M1 shizzle”).

---

### macOS / Linux (bash/zsh)

```bash
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate

# Upgrade pip and install dependencies
pip install --upgrade pip
pip install -r requirements.txt
```

### Windows (PowerShell)
```bash
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
.venv\Scripts\Activate.ps1

# Upgrade pip and install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### Windows (Git Bash)
```bash
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
source .venv/Scripts/activate

# Upgrade pip and install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt
```

You’re now ready to run the session notebooks!

Deactivate the environment when you’re done:
```bash
deactivate
```
