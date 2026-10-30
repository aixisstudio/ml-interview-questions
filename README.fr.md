# Ml Interview Questions

[English](README.md) | **Français** | [Español](README.es.md) | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

Questions d'entretien ML/IA avec réponses types

Entretien avec les personnes atteintes de LM et de l'IA

Les fondamentaux

**Bais/variance d'échange?**
Insuffisance = biais élevé (trop simple). Surfit = variance élevée (mémorise le bruit). La compétence est de trouver le milieu — la régularisation, plus de données, ou des modèles plus simples/complexes.

**Précision ou rappel?**
Précision: de ce que j'ai signalé, combien était juste. Rappel: de ce qui était juste, combien j'ai trouvé. La détection des fraudes favorise le rappel; les filtres antipourriel favorisent la précision.

** Expliquez la suradéquation et 4 façons de la combattre.**
Plus de données · régularisation (L1/L2, abandon) · arrêt précoce · modèle plus simple. En plus: bonne hygiène fractionnée train/test.

**Qu'est-ce qu'une matrice de confusion?**
Grille TP/FP/TN/NF — source de précision, rappel, F1.

Apprentissage profond

**Pourquoi les transformateurs battent les RNN?**
Attention = dépendances parallélisables + à longue distance sans perte de gradient sur la distance. Les RNN sont traitées de façon séquentielle; les transformateurs sont présents dans le monde entier.

**Qu'est-ce que LoRA?**
Adaptation de bas grades — petites matrices injectées fines au lieu de l'ensemble du modèle: adaptateurs bon marché, rapides et compacts.

C'est quoi ?
Modèle de récompense formé sur les préférences humaines → RL (ou DPO) aligne le LLM à eux.

Spécifique au LLM

**Température / top-p / top-k?**
Contrôles d'échantillonnage: température plane/répartir la distribution; top-p (noyau) conserve le plus petit réglage probable; top-k conserve les options k. Moins = plus déterministe.

**RAG vs réglage fin?**
RAG = donner au modèle le contexte de la réponse au moment de la requête (updatable, bon marché). FT = faire cuire la connaissance dans (stable, cher, risque d'oublier). Souvent combinés.

**Hallucination — pourquoi et comment réduire?**
Les modèles prédisent des jetons plausibles, pas la vérité. Réduire via RAG, la sortie limitée, les citations, la basse température, et "disons 'Je ne sais pas' quand on ne sait pas".

Pratique

**Votre modèle est précis à 99 % sur les données de fraude déséquilibrées. Problème?**
L'exactitude n'a pas de sens à 1% de positifs — vérifier la précision/rappel/AUPRC, pas la précision.

**La fuite de données?**
L'information provenant de l'ensemble futur/essai s'infiltre dans la formation — sournoisement par prétraitement (scalage avant scission) ou dupliqués.

Questions appliquées sur le scénario ML

**"La précision du modèle a chuté de 10 % pendant la nuit en prod. Déboguer."**
→ Vérifiez d'abord la dérive des données (distribution des entrées), puis marquez les changements de pipeline, puis un déploiement récent. Ajouter une surveillance sur les distributions de fonctionnalités.

**« Comment traitez-vous le taux positif de 1%? »**
→ N'utilisez pas la précision. PR-AUC, poids de classe, rééchantillonnage, réglage des seuils, pertes sensibles aux coûts. Le cadrage de détection d'anomalie gagne parfois.

**"Train/val est bon mais prod échoue. Pourquoi ?"**
→ Tranche train/serve : différences de pipeline, fuite d'étiquettes dans l'entraînement ou dérive temporelle. Shadow-déploy à comparer.

Théorie du feu rapide

D'après les informations fournies par l'État membre concerné
|---|---|
Un compromis entre la diversité et la diversité?
Pourquoi softmax ? Une argmax différente → probabilités
L1 contre L2?L1 → poids clairsemés; L2 → petits poids
Qu'est-ce que l'abandon? Désactivation aléatoire → effet d'ensemble
Pourquoi normaliser les intrants? Symétrie progressive → convergence plus rapide

Questions d'entrevue (2025)

- Comment évaluez-vous une application LLM ? → Ensembles d'or, Juge LLM, Evales humaines
- Quand fine-tune vs RAG ? → RAG pour les faits, FT pour le style/format
- Qu'est-ce que RLHF ? → Calibrage préférentiel du modèle de récompense + PPO
- Comment réduire les coûts d'inférence ? → Quantité, distill, cache, modèles plus petits

---
## Contribuer

Les pull requests sont les bienvenues : ouvre une PR, elle sera relue et fusionnée. Maintenu par [aixisstudio](https://github.com/aixisstudio), auteur de [Snitch](https://github.com/aixisstudio/Snitch), pare-feu applicatif open source.

## Licence: MIT
