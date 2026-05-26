# FractureFinder-Automated-Classification-of-Bone-Breaks-in-X-rays

AI model able to recognize and arrange diferent kinds of fractures.

<div id="header" align="center">
  <img src="https://github.com/Pipevg1801/FractureFinder-Automated-Classification-of-Bone-Breaks-in-X-rays/blob/main/Recursos_Visuales/Banner_IA.png" />
</div>


## Autores

- [Felipe Vargas Garcia - 2230033](https://github.com/Pipevg1801)
- Juan Felipe Serrano Contreras - 2230088
- Javier Gomez Villaruel - 2230956

## Índice
1. [Objetivo](#objetivo)
2. [Motivación y Descripción del problema](#motivación-y-descripción-del-problema)
3. [Descripción del Dataset](#descripción-del-dataset)
4. [Preprocesamiento](#preprocesamiento)
5. [Modelos utilizados](#modelos-utilizados)
6. [Conclusiones](#conclusiones)
7. [Enlaces](#enlaces)

## Objetivo
Desarrollar un sistema automatizado capaz de detectar, clasificar y localizar fracturas óseas a partir de imágenes de rayos X, utilizando técnicas de visión por computadora para asistir en el diagnóstico médico.

## Motivación y Descripción del problema
La interpretación de radiografías para detectar fracturas es una tarea crítica en el ámbito médico. El problema radica en la complejidad visual de las fracturas óseas, que pueden ser sutiles o difíciles de categorizar. Este proyecto busca implementar algoritmos de inteligencia artificial para estandarizar y agilizar el proceso de clasificación, reduciendo la carga de trabajo y el margen de error humano.

## Descripción del Dataset
Se utilizó el dataset *["Bone Break Classification Image Dataset"](https://www.kaggle.com/datasets/pkdarabi/bone-break-classification-image-dataset)*, compuesto por imágenes de rayos X.
* **Total de imágenes**: 1129.
* **Entrenamiento**: 989 imágenes.
* **Prueba**: 140 imágenes.
* **Categorías**: Incluye diversas partes del cuerpo (codo, antebrazo, rodilla, etc.) y múltiples tipos de fracturas (avulsión, conminuta, tallo verde, oblicua, entre otras).

## Preprocesamiento
Para preparar las imágenes para los modelos, se realizaron las siguientes operaciones:
* Lectura y carga de subcarpetas de entrenamiento.
* Conversión de las imágenes a escala de grises.
* Redimensionamiento de todas las imágenes a un tamaño estandarizado de **256x256 píxeles**.

## Modelos utilizados
El proyecto exploró **diversos métodos de aprendizaje automático para la clasificación y agrupamiento de imágenes de fracturas óseas**. Los modelos de clasificación supervisada evaluados fueron:
*   **Árbol de Decisión (Decision Tree)**: Un modelo de clasificación basado en un árbol, utilizado para predecir la clase de fractura.
*   **Bosque Aleatorio (Random Forest)**: Un método de conjunto que combina múltiples árboles de decisión para mejorar la precisión y reducir el sobreajuste.
*   **Máquinas de Vectores de Soporte (SVM - Support Vector Machine)**: Un clasificador que busca el hiperplano óptimo para separar las clases en el espacio de características.
*   **Perceptrón Multicapa (MLP - Multi-layer Perceptron) con TensorFlow**: Una red neuronal simple para clasificación, que se probó tanto con 10 clases como con 2 clases seleccionadas.
Para la reducción de dimensionalidad y visualización, se empleó:
*   **Análisis de Componentes Principales (PCA)**: Utilizado para transformar las características de la imagen a un espacio de menor dimensión, facilitando la visualización de la distribución de clases y el agrupamiento.
En cuanto a los métodos de clustering no supervisado, se probaron:
*   **K-Means (k=2)**: Se utilizó con el objetivo de agrupar los datos en clusters, aunque se concluyó que los grupos formados no coincidían con las categorías médicas reales, mostrando que la división geométrica no tiene significado clínico.
*   **DBSCAN**: Un algoritmo de clustering basado en densidad, que resultó insuficiente dado que los datos no presentan variaciones de densidad significativas tras la proyección en 2D con PCA, categorizando la mayoría de los puntos como ruido.

**Nota**: Se determinó que los métodos tradicionales basados en píxeles crudos y características de baja dimensionalidad no son suficientes para esta tarea compleja de clasificación de fracturas, sugiriendo la necesidad de implementar **Deep Learning** (específicamente Redes Neuronales Convolucionales) para una mejor extracción de características y un rendimiento más robusto.

## Conclusiones
* Los métodos de clustering tradicionales como K-Means y DBSCAN no son óptimos para este conjunto de datos, ya que no logran capturar las características semánticas necesarias para diferenciar tipos de fracturas médicas.
* La homogeneidad de las imágenes proyectadas impide que los algoritmos no supervisados encuentren separaciones claras, confirmando que se requieren modelos de aprendizaje profundo (como redes neuronales convolucionales) para abordar la complejidad de este problema clínico.

## Enlaces
* [Dataset original en Kaggle](https://www.kaggle.com/datasets/pkdarabi/bone-break-classification-image-dataset)
* [Repositorio del proyecto](https://github.com/Pipevg1801/FractureFinder-Automated-Classification-of-Bone-Breaks-in-X-rays.git)
