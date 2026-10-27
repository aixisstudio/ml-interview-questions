# Ml Interview Questions

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh-CN.md) | **日本語** | [Русский](README.ru.md)

ML 面接の質問と回答

_詳細なコンテンツ（リスト・リンク・説明）は保守のため英語です。以下のセクションがガイドになります。_

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

## 🧪 Applied ML scenario questions

**"Model accuracy dropped 10% overnight in prod. Debug."**
→ Check data drift first (input distribution), then label pipeline changes, then a recent deploy. Add monitoring on feature distributions.

**"How do you handle 1% positive rate?"**
→ Don't use accuracy. PR-AUC, class weights, resampling, threshold tuning, cost-sensitive losses. Anomaly-detection framing sometimes wins.

**"Train/val is fine but prod fails. Why?"**
→ Train/serve skew: feature pipeline differences, label leakage in training, or time-based drift. Shadow-deploy to compare.

## 🧮 Quick-fire theory

| Q | A |
|---|---|
| Bias-variance tradeoff? | Simple models underfit (bias), complex overfit (variance) |
| Why softmax? | Differentiable argmax → probabilities |
| L1 vs L2? | L1 → sparse weights; L2 → small weights |
| What is dropout? | Random deactivation → ensemble effect |
| Why normalize inputs? | Gradient symmetry → faster convergence |

## 🤖 LLM interview questions (2025)

- How do you evaluate an LLM app? → Golden sets, LLM-judge, human evals
- When fine-tune vs RAG? → RAG for facts, FT for style/format
- What is RLHF? → Reward-model + PPO preference tuning
- How to cut inference cost? → Quantize, distill, cache, smaller models

---
## 貢献

プルリクエストを歓迎します。レビューしてマージします。[aixisstudio](https://github.com/aixisstudio) による管理 — オープンソースのアプリケーションファイアウォール [Snitch](https://github.com/aixisstudio/Snitch) の作者です。

## ライセンス: MIT
