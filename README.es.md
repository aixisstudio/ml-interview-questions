# Ml Interview Questions

[English](README.md) | [Français](README.fr.md) | **Español** | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

Preguntas de entrevista ML con respuestas

## 🎯 ML &amp; AI interview Q

### Fundamentals

**Bias / cambio de variación?**
Infit = sesgo alto (demasiado simple). Overfit = alta diferencia (memoriza el ruido). La habilidad es encontrar el medio - regularización, más datos, o modelos más simples / complejos.

¿Precisión contra memoria?
Precisión: de lo que señalé, cuánto tenía razón. Recordad: de lo que era correcto, cuánto encontré. La detección del fraude favorece el recuerdo; los filtros de spam favorecen la precisión.

**Explicar el exceso de ajuste y 4 formas de combatirlo.**
Más datos · regularización (L1/L2, abandono) · parada temprana · modelo más simple. Además: adecuado tren / prueba de higiene dividida.

¿Qué es una matriz de confusión?
TP/FP/TN/FN grid — fuente de precisión, memoria, F1.

## Deep learning

**¿Por qué los transformadores golpearon RNNs?**
Atención = dependencias paralelas + de largo alcance sin perder el gradiente a lo largo de la distancia. Las RNN procesan secuencialmente; los transformadores asisten a nivel mundial.

¿Qué es LoRA?
Adaptación de bajo rango — matrices inyectables de punta en lugar de todo el modelo: adaptadores baratos, rápidos y composables.

¿RLHF?
Modelo de recompensa entrenado en las preferencias humanas → RL (o DPO) alinea el LLM a ellos.

#### LLM-specific

**Temperatura / top-p / top-k?**
Controles de muestreo: temperaturas planas / sharpens la distribución; top-p (nucleus) mantiene el conjunto más pequeño posible; top-k mantiene opciones k. Bajo = más determinista.

**RAG vs fine-tuning?**
RAG = dar al modelo el contexto de la respuesta en el tiempo de consulta (updatable, barato). FT = conocimiento de hornear en (estable, costoso, riesgo olvidando). A menudo combinado.

**Alucinación: ¿por qué y cómo reducir?**
Los modelos predicen fichas plausibles, no verdad. Reduzca a través de RAG, salida limitada, citas, baja temperatura, y "dije 'No lo sé' cuando no está seguro" pide.

################################################################################################################################################################################################################################################################

**Su modelo es 99% exacto en datos de fraude desbalanzados. ¿Problema?
La precisión no tiene sentido al 1% de los positivos: comprobar la precisión/recall/AUPRC, no la precisión.

¿Una fuga de datos?
Información del futuro/test set filtrando en el entrenamiento – escurridizo a través del preprocesamiento (scaling before split) o los registros duplicados.

## 🧪 Applied ML scenario questions

**"La precisión del modelo cayó un 10% durante la noche en prod. Debug."
→ Compruebe los datos deriva primero (distribución de entrada), luego los cambios de tubería de etiquetado, luego un despliegue reciente. Agregue el monitoreo en las distribuciones de características.

** "¿Cómo se maneja una tasa positiva del 1%?"**
→ No use la precisión. PR-AUC, pesos de clase, muestreo, ajuste del umbral, pérdidas sensibles al costo. El encuadre de detección a veces gana.

**El tren/val está bien pero el prod falla. ¿Por qué?
→ Diferencia del tren/servido: diferencias de tuberías, filtración de etiquetas en el entrenamiento o deriva basada en el tiempo. Despliegue de sombras para comparar.

## 🧮 Quick-fire theory

Silencio
|---|---|
← Bias-variance tradeoff?
¿Por qué softmax? Silencio Diferente argmax → probabilidades
TEN L1 vs L2? TEN L1 → pesas escasas; L2 → pesos pequeños TEN
¿Qué es el abandono? ← Desactivación aleatoria → efecto ensemble
¿Por qué normalizar las entradas? Simetría gradiente   convergencia más rápida

## 🤖 LLM interview questions (2025)

- ¿Cómo evalúas una aplicación LLM? → Golden sets, LLM-juez, evals humanos
- ¿Cuándo el fino vs. RAG? → RAG para hechos, FT para estilo/format
- ¿Qué es RLHF? → Moda de recompensa + ajuste de preferencia PPO
- ¿Cómo reducir el costo de la inferencia? → Cuantizar, destilar, cache, modelos más pequeños

---
## Contribuir

Los pull requests son bienvenidos: abre una PR y será revisada y fusionada. Mantenido por [aixisstudio](https://github.com/aixisstudio), autor de [Snitch](https://github.com/aixisstudio/Snitch), firewall de aplicaciones open source.

## Licencia: MIT
