Time-Series-Forecasting-for-Particles-PMCO-in-CDMX
# Evaluación de un Modelo Basado en Transformers para el Pronóstico Temporal de Concentraciones de Material Particulado Coarse (PMCO)

Artículo (Overleaf): https://www.overleaf.com/read/sbwhtrdfvjpp

Code (Google colab): https://colab.research.google.com/drive/1dC-TTHUn46UtAEthWut3zgTQQ2YpShad?usp=sharing

---

## Introduction

El pronóstico de series temporales es un problema esencial en numerosos campos, desde la ciencia y la tecnología hasta los negocios y la economía. En este contexto, las partículas en suspensión, conocidas como Particulate Matter (PM), representan un importante problema de salud pública y medioambiental, especialmente en áreas urbanas densamente pobladas como la Ciudad de México. Las partículas ultrafinas o partículas fracción gruesa (PMCO), son de especial interés debido a su capacidad de penetrar profundamente en los pulmones y en el torrente sanguíneo. Estas partículas son de tamaño micrométrico, específicamente, entre los valores de 2.5 μm o 10 μm de diámetro.

Para nuestro estudio, utilizaremos datos proporcionados por la Red Automática de Monitoreo Atmosférico (RAMA), una iniciativa gestionada por la Secretaría de Medio Ambiente de la Ciudad de México (SEDEMA). La RAMA es responsable de monitorear y registrar la calidad del aire en la Ciudad de México, una de las metrópolis más grandes del mundo. En este estudio, nos enfocamos en las partículas fracción gruesa (PMCO), que son de especial interés debido a su capacidad de penetrar profundamente en los pulmones y en el torrente sanguíneo.

## Selección de Datos

Para asegurar la relevancia y la fiabilidad de nuestro análisis, hemos seleccionado la base de datos de RAMA correspondiente a los años 2014-2018. Esta elección se fundamenta en dos consideraciones clave:

- **Estabilidad Temporal**: Optamos por estudiar los cinco años más estables y próximos a la actualidad. Tomamos la decisión de evitar los años 2019-2021, ya que la pandemia de SARS-CoV-2 impuso condiciones atípicas en la Ciudad de México (y en el mundo). La implementación de medidas como el trabajo y las escuelas virtuales, así como restricciones a la movilidad, redujeron significativamente el tráfico vehicular y modificaron de diversas maneras el comportamiento de la población. Esto, a su vez, tuvo un impacto en los niveles de contaminación del aire, lo que podría afectar la generalización de nuestros modelos de pronóstico.

- **Calidad de los Datos**: Para nuestro análisis, seleccionamos las estaciones de monitoreo que presentan los registros más completos y confiables. Esto significa elegir las estaciones con la menor cantidad de datos faltantes durante el periodo de estudio. Esta selección meticulosa nos permite trabajar con un conjunto de datos robusto y representativo, minimizando la necesidad de imputar o interpolar datos faltantes.

##  Probabilistic Forecasting

Más allá de prever un único valor futuro (pronóstico de punto), es crucial estimar la incertidumbre asociada a dichas predicciones. Esto es lo que se conoce como "pronóstico probabilístico". En lugar de entrenar modelos de pronóstico de punto locales, esta investigación busca entrenar modelos probabilísticos globales. Estos modelos, al estar fundamentados en el aprendizaje profundo, tienen la capacidad de aprender representaciones latentes a partir de múltiples series temporales y modelar la incertidumbre asociada a los datos, lo cual es fundamental para una toma de decisiones informada.

## The Time Series Transformer

Para abordar la complejidad de los datos de series temporales, que son intrínsecamente secuenciales, se han explorado diversas arquitecturas de redes neuronales, incluyendo Redes Neuronales Recurrentes (RNN), como las LSTM o GRU, y Redes Convolucionales (CNN). Sin embargo, más recientemente, los Transformers han emergido como una herramienta poderosa para modelar datos secuenciales.

En esta investigación, adoptamos el Transformers, propuesto inicialmente por Vaswani et al. (2017), para la tarea de pronóstico probabilístico univariado de PMCO. La arquitectura Codificador-Decodificador del Transformers es una elección natural para el pronóstico de series temporales, ya que permite generar predicciones a varios pasos en el futuro a partir de datos observados, similar a cómo se generaría texto de manera autoregresiva en tareas de Procesamiento de Lenguaje Natural (NLP).

Esta investigación aborda también los desafíos asociados con el uso de Transformers, como la selección de ventanas de contexto y predicción adecuadas, la incorporación de valores faltantes mediante el uso de máscaras, y la limitación computacional debido a los requisitos cuadráticos de cálculo y memoria del Transformers vainilla.

## Objetivos de la Investigación

### Objetivo General

- Evaluar la eficacia de un modelo basado en Transformers en el pronóstico temporal de las concentraciones de Material Particulado Coarse (PMCO) con el fin de determinar su potencial como herramienta de predicción de alta precisión y eficiencia.

### Objetivos Específicos

1. **Recopilación de Datos:** 
    - Recopilar y preparar un conjunto de datos históricos de concentraciones de Material Particulado Coarse (PMCO) y características temporales relevantes que servirán como entrada para el modelo. Esto incluirá datos de la Red Automática de Monitoreo Atmosférico (RAMA) gestionada por la Secretaría de Medio Ambiente de la Ciudad de México (SEDEMA) para el periodo 2014-2018.

2. **Revisión Bibliográfica:** 
    - Realizar una revisión bibliográfica exhaustiva sobre la contaminación del aire por partículas PMCO, sus efectos sobre la salud y el medio ambiente, y los métodos existentes para su monitoreo y pronóstico. 

3. **Evaluación del Modelo:** 
    - Evaluar el rendimiento del modelo basado en Transformers utilizando métricas de evaluación apropiadas, con el objetivo de determinar si este modelo es capaz de superar las limitaciones en precisión y eficiencia que presentan las herramientas de pronóstico actuales.

4. **Optimización y Propuestas Futuras:** 
    - Identificar y proponer posibles mejoras y extensiones al modelo. Sugerir áreas de investigación futura relacionadas con la aplicación de modelos basados en Transformers en pronósticos ambientales.

## Hipótesis de la Investigación

Al utilizar datos históricos de concentraciones de Material Particulado Coarse (PMCO) y características temporales como variables de entrada, los modelos basados en Transformers, que han demostrado ser efectivos en capturar dependencias a largo plazo en tareas de procesamiento de lenguaje natural, serán capaces de generar predicciones precisas de concentraciones futuras de PMCO como variable de salida. Esto se basa en el supuesto de que existen patrones temporales en las concentraciones de PMCO que pueden ser capturados por estos modelos.
