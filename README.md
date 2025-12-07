# FruitQuality - Detector de Defectos en Frutas 🍎🐛
Este repositorio documenta el desarrollo de un sistema de visión por computador diseñado para detectar defectos en frutas, con el objetivo de automatizar el control de calidad en líneas de producción. El proyecto explora desde técnicas básicas de procesamiento de imagen hasta algoritmos más robustos para adaptarse a diferentes tipos de frutas y defectos.


## 🚀 Evolución del Proyecto

El desarrollo se ha dividido en fases iterativas, abordando desafíos específicos en cada etapa:

Parte 1: Detección Básica (Manzanas Claras)
Objetivo: Detectar grandes áreas de podredumbre oscura en manzanas de piel clara.

Técnica: Combinación de detección de bordes (Sobel) y análisis de color (LUT/HSV).

Resultado: Efectivo para defectos de alto contraste y gran tamaño.


Parte 2: Robustez y Generalización
Mejora: Implementación del Método de Otsu para la umbralización automática, eliminando la dependencia de valores fijos de iluminación.

Mejora: Introducción de operaciones morfológicas (apertura/cierre) para limpiar el ruido y reducir falsos positivos.

Resultado: Un sistema capaz de adaptarse a variaciones de luz, ideal para defectos tipo "golpe" o "podredumbre" en frutas claras.

Parte 3: Detección Avanzada en Entornos Complejos
Mejora: Eliminación del fondo de la imagen con ayuda del modelo YOLOv8-seg.

Resultado: El modelo "entiende" la forma del objeto. Sabe distinguir entre distintos objetos con el mismo color y elegir el favorable, detectando la más grande que se encuentre en la imagen.



## 🛠️ Tecnologías Utilizadas

Python 3.12

OpenCV (cv2): Procesamiento de imágenes, operaciones morfológicas, detección de contornos.

NumPy: Manipulación de matrices y cálculos numéricos.

Matplotlib: Visualización de resultados y etapas intermedias.

Ultralytics: Detección y segmentación de instancias en tiempo real.



## 📂 Estructura del Repositorio

/images: Banco de imágenes de prueba (ManzanaB, ManzanaM, ManzanaGusano, Pera, etc.).

Parte-1.ipynb: Prototipo inicial con detección por gradientes y LUT.

Parte-2.ipynb: Versión mejorada con Otsu y fusión lógica de bordes/color.

Parte-2.1.ipynb: Pruebas con diferentes manzanas donde se observa de forma más clara el fallo.

Parte-2.2.ipynb: Pruebas con diferentes frutas para comprobar que se detecta todo de manera clara.



## ✨ Cómo Ejecutar

1. Clona el repositorio.

2. Asegúrate de tener las librerías necesarias: pip install opencv-python numpy matplotlib

3. Ejecuta los notebooks o scripts apuntando a tus imágenes en la carpeta /images.
