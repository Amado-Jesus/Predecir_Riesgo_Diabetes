# 🥼 Predicción de Riesgo de Diabetes

## 📌 Resumen

Este proyecto consiste en el desarrollo de una aplicación web interactiva construida con Streamlit, cuyo objetivo es permitir a los profesionales de la salud cargar datos clínicos de pacientes en formato CSV para clasificar su riesgo de diabetes, utilizando un modelo de Máquinas de Soporte Vectorial (SVM) previamente entrenado y optimizado.
La aplicación se enfoca en la rapidez diagnóstica y la seguridad del paciente, evitando el reentrenamiento del modelo y ofreciendo resultados inmediatos de clasificación de riesgo (Bajo/Alto), priorizando la máxima sensibilidad para no perder casos positivos en el screening.

| Problema en Salud Pública                         | Solución de la Aplicación                                   |
| ------------------------------------------------- | ----------------------------------------------------------- |
| **Alta prevalencia de diabetes no diagnosticada** | Screening masivo automatizado con recall del 95.7%          |
| **Escasez de especialistas endocrinólogos**       | Triage inteligente que prioriza pacientes de alto riesgo    |
| **Tiempos de espera prolongados**                 | Resultados inmediatos tras carga de archivo CSV             |
| **Variabilidad en criterios clínicos**            | Estandarización mediante modelo SVM validado                |
| **Pérdida de pacientes en seguimiento**           | Identificación temprana de riesgo antes de síntomas severos |


---

## 🧠 Descripción del Proyecto
Sistema de screening diabético basado en SVM que procesa 8 biomarcadores clínicos vía CSV para clasificar riesgo (Bajo/Alto) en segundos, sin reentrenamiento, con 95.7% de sensibilidad. Solución práctica de ML para atención primaria.

---

## 📊 Modelo de Machine Learning

| Elemento             | Descripción                                                                             |
| -------------------- | --------------------------------------------------------------------------------------- |
| **Usuario**          | Profesional de salud (médicos, enfermeras, laboratoristas)                              |
| **Inputs**           | Sexo, edad, IMC, glucosa en suero, triglicéridos, colesterol HDL, insulina, ácido úrico |
| **Modelo**           | SVM clasificación con **kernel lineal optimizado**                                      |
| **Output**           | Clasificación binaria: Bajo Riesgo / Alto Riesgo                                        |
| **Propósito**        | Screening médico preventivo de diabetes mellitus tipo 2                                 |
| **Entorno**          | Atención primaria y laboratorios clínicos                                               |
| **Impacto**          | Detección temprana, reducción de complicaciones severas                                 |
| **Métrica clave**    | Recall (sensibilidad): 95.7%                                                            |
| **Formato datos**    | Archivo CSV con carga masiva                                                            |
| **Latencia**         | Resultados inmediatos (< 1 segundo por lote)                                            |
| **Preprocesamiento** | **PowerTransformer** (transformación de potencia) + codificación de sexo                |
| **Optimización**     | Validación cruzada 5-fold, métrica recall ponderado                                     |

| Aspecto                        | Detalle                                                                                                          |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| **PowerTransformer**           | Transformación de Yeo-Johnson o Box-Cox para normalizar distribuciones asimétricas de variables biomarcadoras    |
| **Ventaja vs. StandardScaler** | Mejor manejo de datos con colas pesadas (ej: triglicéridos, insulina frecuentemente sesgados)                    |
| **Kernel lineal SVM**          | Hiperplano de separación lineal, más interpretable y eficiente computacionalmente que RBF con datasets moderados |

---

## 🖥️ Aplicación Web con Streamlit

El archivo `new_data.csv` es una muestra del formato requerido por la aplicación.

Este archivo sirve como referencia para que el usuario conozca cómo debe estructurar los datos antes de cargarlos en el sistema.

La aplicación utiliza archivos con esta misma estructura para procesar nuevos pacientes y generar predicciones de riesgo de diabetes.


La aplicación web fue desarrollada con [Streamlit App](https://riesgodiabetesapp-2ecsesokgsejq2utsesm8p.streamlit.app/ )  y cuenta con:
* Carga de archivo CSV para ingreso masivo de datos de pacientes (8 variables biomarcadoras).
* Botón para generar la clasificación de riesgo diabético (Bajo/Alto).
* Descarga del dataset enriquecido con la columna de predicciones.
* Carga del modelo SVM sin necesidad de reentrenarlo.
* Interfaz sencilla e intuitiva optimizada para personal de salud.

---
