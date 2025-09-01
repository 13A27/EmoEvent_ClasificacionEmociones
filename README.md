# Clasificación de Emociones en Tweets (EmoEvent)

Este repositorio contiene un estudio exploratorio de *clasificación de emociones en español* usando el dataset [*EmoEvent*](https://github.com/fmplaza/EmoEvent/tree/master/splits).  
El objetivo es comparar diferentes enfoques (léxicos, lingüísticos y contextuales) para predecir una de las *8 categorías: *anger, sadness, joy, disgust, fear, surprise, offensive, other.

---

## Contenido del repositorio

- EmoEvent_ClasificacionEmociones_Notebook.ipynb → notebook principal con todo el flujo:
  - Preprocesamiento y limpieza de datos
  - Exploración y análisis descriptivo (EDA)
  - Entrenamiento y evaluación de tres modelos
  - Reportes de métricas por clase y por evento
  - Matrices de confusión y análisis comparativo
- Carpeta /results:
  - Tablas y métricas exportadas
  - Gráficos de desempeño guardados en *formato .jpeg* (matrices de confusión, distribuciones de clases, comparaciones entre modelos)
- README.md → este archivo

---

## Modelos explorados

1. *Modelo 1 — TF-IDF + Logistic Regression*  
   - Palabras (1–2-gramas + hashtags) y caracteres (4–5-gramas).  
   - Clasificación multiclase con Regresión Logística.

2. *Modelo 2 — spaCy ES (POS/DEP enriquecido) + Logistic Regression*  
   - B-POS: secuencias de lemmas (NOUN, VERB, ADJ, ADV).  
   - B-DEP+rel: plantillas de dependencias sintácticas.  
   - Clasificación multiclase con Regresión Logística.

3. *Modelo 3 — Fine-tuning con BETO (TF/Keras)*  
   - Backbone: dccuchile/bert-base-spanish-wwm-uncased.  
   - Entrenamiento con Adam, class_weight, EarlyStopping.  

---

## Resultados en formato JPEG

Los resultados principales se encuentran en la carpeta /results:

- *Matrices de confusión* → muestran cómo cada modelo confunde entre emociones.  
- *Distribuciones de clases* → frecuencia por emoción en cada split.  
- *Comparaciones entre modelos* → gráficas de F1/accuracy.  

