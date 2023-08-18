Time-Series-Forecasting-for-Particles-PMCO-in-CDMX
# Evaluación de un Modelo Basado en Transformers para el Pronóstico Temporal de Concentraciones de Material Particulado Coarse (PMCO)

Artículo (Overleaf): https://www.overleaf.com/read/sbwhtrdfvjpp

Code (Google colab): https://colab.research.google.com/drive/1dC-TTHUn46UtAEthWut3zgTQQ2YpShad?usp=sharing

---

## Introduction

El pronóstico de series temporales es crucial en diversos campos, incluyendo ciencia, tecnología, negocios y economía. Un aspecto significativo de salud pública y medioambiental es la concentración de partículas en suspensión, o Particulate Matter (PM), especialmente en áreas urbanas densas como la Ciudad de México. Las partículas fracción gruesa (PMCO), con tamaños micrométricos entre 2.5 μm y 10 μm de diámetro, son de especial preocupación debido a su capacidad de penetrar en los pulmones y el torrente sanguíneo. Para el estudio, se utilizarán datos proporcionados por la Red Automática de Monitoreo Atmosférico (RAMA), gestionada por la Secretaría de Medio Ambiente de la Ciudad de México (SEDEMA). RAMA tiene la responsabilidad de monitorear y registrar la calidad del aire en esta gran metrópolis. El estudio se enfoca específicamente en las partículas PMCO.

## Data

Para asegurar la relevancia y la fiabilidad de nuestro análisis, hemos seleccionado la base de datos de RAMA correspondiente a los años 2014-2018. Esta elección se fundamenta en dos consideraciones clave:

- **Estabilidad Temporal**: Optamos por estudiar los cinco años más estables y próximos a la actualidad. Tomamos la decisión de evitar los años 2019-2021, ya que la pandemia de SARS-CoV-2 impuso condiciones atípicas en la Ciudad de México (y en el mundo). 

- **Calidad de los Datos**: Para nuestro análisis, seleccionamos las estaciones de monitoreo que presentan los registros más completos y confiables. Esto significa elegir las estaciones con la menor cantidad de datos faltantes durante el periodo de estudio y que estos datos faltantes esten lo mejor distribuidos. 

##  Probabilistic Forecasting

Más allá de prever un único valor futuro (pronóstico de punto), es crucial estimar la incertidumbre asociada a dichas predicciones. Esto es lo que se conoce como "pronóstico probabilístico". En lugar de entrenar modelos de pronóstico de punto locales, esta investigación busca entrenar modelos probabilísticos globales. Estos modelos, al estar fundamentados en el aprendizaje profundo, tienen la capacidad de aprender representaciones latentes a partir de múltiples series temporales y modelar la incertidumbre asociada a los datos, lo cual es fundamental para una toma de decisiones informada.

## The Time Series Transformer

Para abordar la complejidad de los datos de series temporales, que son intrínsecamente secuenciales, se han explorado diversas arquitecturas de redes neuronales, incluyendo Redes Neuronales Recurrentes (RNN), como las LSTM o GRU, y Redes Convolucionales (CNN). Sin embargo, más recientemente, los Transformers han emergido como una herramienta poderosa para modelar datos secuenciales.

En esta investigación, adoptamos el Transformers, propuesto inicialmente por Vaswani et al. (2017), para la tarea de pronóstico probabilístico univariado de PMCO. La arquitectura Codificador-Decodificador del Transformers es una elección natural para el pronóstico de series temporales, ya que permite generar predicciones a varios pasos en el futuro a partir de datos observados, similar a cómo se generaría texto de manera autoregresiva en tareas de Procesamiento de Lenguaje Natural (NLP).

Esta investigación aborda también los desafíos asociados con el uso de Transformers, como la selección de ventanas de contexto y predicción adecuadas, la incorporación de valores faltantes mediante el uso de máscaras, y la limitación computacional debido a los requisitos cuadráticos de cálculo y memoria del Transformers vainilla.

## Objetivos de la Investigación

### Objetivo General

- Evaluar la eficacia de un modelo basado en Transformers en el pronóstico temporal de las concentraciones de Material Particulado Coarse (PMCO) con el fin de determinar su potencial como herramienta de predicción de alta precisión y eficiencia. Probandolo para el forecasting de 6,9,12,24...

## Hipótesis de la Investigación

Al utilizar datos históricos de concentraciones de Material Particulado Coarse (PMCO) y características temporales como variables de entrada, los modelos basados en Transformers, que han demostrado ser efectivos en capturar dependencias a largo plazo en tareas de procesamiento de lenguaje natural, serán capaces de generar predicciones precisas de concentraciones futuras de PMCO como variable de salida. Esto se basa en el supuesto de que existen patrones temporales en las concentraciones de PMCO que pueden ser capturados por estos modelos.

---
---

<span>![</span><span>Aquí la descripción de la imagen por si no carga</span><span>]</span><span>(</span><span>https://raw.githubusercontent.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/main/Plots/6-HGM.png</span><span>)</span>

**HGM | RMSE: 6.324176146230774**
