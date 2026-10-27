# Ml Interview Questions

[English](README.md) | [Français](README.fr.md) | **Español** | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

Preguntas de entrevista ML con respuestas

_El contenido detallado (listas, enlaces, descripciones) está en inglés por mantenibilidad — las secciones siguientes te guían._

## 🎯 ML & AI interview Q&A

### Fundamentals

**Bias/variance tradeoff?**
Underfit = high bias (too simple). Overfit = high variance (memorizes noise). The skill is finding the middle — regularization, more data, or simpler/complexer models.

**Precision vs recall?**
Precision: of what I flagged, how much was right. Recall: of what was right, how much I found. Fraud detection favors recall; spam filters favor precision.

**Explain overfitting and 4 ways to fight it.**
More data · regularization (L1/L2, dropout) · early stopping · simpler model. Plus: proper train/test split hygiene.

**What's a confusion matrix?**
TP/FP/TN/FN grid — the source of precision, recall, F1.

### Deep learning

**Why transformers beat RNNs?**
Attention = parallelizable + long-range dependencies without vanishing gradient over distance. RNNs processed sequentially; transformers attend globally.

**What is LoRA?**
Low-rank adaptation — fine-tunes small injected matrices instead of the whole model: cheap, fast, composable adapters.

**RLHF?**
Reward model trained on human preferences → RL (or DPO) aligns the LLM to them.

### LLM-specific

**Temperature / top-p / top-k?**
Sampling controls: temperature flattens/sharpens the distribution; top-p (nucleus) keeps the smallest probable set; top-k keeps k options. Lower = more deterministic.

**RAG vs fine-tuning?**
RAG = give the model the answer's context at query time (updatable, cheap). FT = bake knowledge in (stable, expensive, risks forgetting). Often combined.

**Hallucination — why and how to reduce?**
Models predict plausible tokens, not truth. Reduce via RAG, constrained output, citations, low temperature, and "say 'I don't know' when unsure" prompts.

### Practical

**Your model is 99% accurate on imbalanced fraud data. Problem?**
Accuracy is meaningless at 1% positives — check precision/recall/AUPRC, not accuracy.

**Data leakage?**
Information from the future/test set leaking into training — sneaky via preprocessing (scaling before split) or duplicated records.

---
## Contribuir

Los pull requests son bienvenidos: abre una PR y será revisada y fusionada. Mantenido por [aixisstudio](https://github.com/aixisstudio), autor de [Snitch](https://github.com/aixisstudio/Snitch), firewall de aplicaciones open source.

## Licencia: MIT
