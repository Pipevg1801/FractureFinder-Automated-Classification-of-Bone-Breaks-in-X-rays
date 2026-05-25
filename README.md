# FractureFinder-Automated-Classification-of-Bone-Breaks-in-X-rays

AI model able to recognize and arrange diferent kinds of fractures.

<div id="header" align="center">
  <img src="https://github.com/Pipevg1801/FractureFinder-Automated-Classification-of-Bone-Breaks-in-X-rays/blob/main/Recursos_Visuales/Banner_IA.png" />
</div>


## Autores

- [Felipe Vargas Garcia - 2230033](https://github.com/popcorner893)
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
El proyecto exploró métodos de aprendizaje automático para clasificación:
* **K-Means ($k=4$)**: Utilizado para intentar agrupar los datos, aunque se concluyó que los grupos formados no coincidían con las categorías médicas.
* **DBSCAN**: Algoritmo de clustering basado en densidad, que resultó insuficiente dado que los datos no presentan variaciones de densidad significativas tras la proyección en 2D.
* **Nota**: Se determinó que los métodos tradicionales basados en píxeles crudos no son suficientes, sugiriendo la necesidad de implementar **Deep Learning** para una mejor extracción de características.

## Conclusiones
* Los métodos de clustering tradicionales como K-Means y DBSCAN no son óptimos para este conjunto de datos, ya que no logran capturar las características semánticas necesarias para diferenciar tipos de fracturas médicas.
* La homogeneidad de las imágenes proyectadas impide que los algoritmos no supervisados encuentren separaciones claras, confirmando que se requieren modelos de aprendizaje profundo (como redes neuronales convolucionales) para abordar la complejidad de este problema clínico.

## Enlaces
* [Dataset original en Kaggle](https://www.kaggle.com/datasets/pkdarabi/bone-break-classification-image-dataset)
* [Repositorio del proyecto](https://github.com/Pipevg1801/FractureFinder-Automated-Classification-of-Bone-Breaks-in-X-rays.git)