# FruitQuality - Detector de Defectos en Frutas 🍎🐛
Este repositorio documenta el desarrollo de un sistema de visión por computador diseñado para detectar defectos en frutas, con el objetivo de automatizar el control de calidad en líneas de producción. El proyecto explora desde técnicas básicas de procesamiento de imagen hasta algoritmos más robustos para adaptarse a diferentes tipos de frutas y defectos.

🚀 Evolución del Proyecto

El desarrollo se ha dividido en fases iterativas, abordando desafíos específicos en cada etapa:

Parte 1: Detección Básica (Manzanas Claras)
Objetivo: Detectar grandes áreas de podredumbre oscura en manzanas de piel clara (amarilla/verde).

Técnica: Combinación de detección de bordes (Sobel/Canny) y análisis de color (LUT/HSV).

Resultado: Efectivo para defectos de alto contraste y gran tamaño.

Parte 2: Robustez y Generalización
Mejora: Implementación del Método de Otsu para la umbralización automática, eliminando la dependencia de valores fijos de iluminación.

Mejora: Introducción de operaciones morfológicas (apertura/cierre) para limpiar el ruido y reducir falsos positivos.

Resultado: Un sistema capaz de adaptarse a variaciones de luz, ideal para defectos tipo "golpe" o "podredumbre" en frutas claras.

Parte 3: El Desafío del Bajo Contraste (Manzanas Rojas) 🔴
Problema: Los métodos anteriores fallaban al detectar defectos oscuros (como agujeros de gusano) sobre pieles oscuras (manzanas rojas), confundiendo la piel sana con el defecto.

Solución Innovadora: Implementación de separación de canales de color. Al analizar exclusivamente el Canal Rojo, se maximiza el contraste físico entre la piel (que refleja mucho rojo) y el defecto (que lo absorbe), permitiendo una segmentación precisa mediante umbralización simple y filtrado por circularidad.



🛠️ Tecnologías Utilizadas

Python 3.12

OpenCV (cv2): Procesamiento de imágenes, operaciones morfológicas, detección de contornos.

NumPy: Manipulación de matrices y cálculos numéricos.

Matplotlib: Visualización de resultados y etapas intermedias.

📂 Estructura del Repositorio

/images: Banco de imágenes de prueba (ManzanaB, ManzanaM, ManzanaGusano, Pera, etc.).

Parte-1.ipynb: Prototipo inicial con detección por gradientes y LUT.

Parte-2.ipynb: Versión mejorada con Otsu y fusión lógica de bordes/color.

Parte-3-Canales.py (o el nombre que le des al último script): Solución final basada en canales de color para frutas de piel oscura.

✨ Cómo Ejecutar

Clona el repositorio.

Asegúrate de tener las librerías necesarias:
pip install opencv-python numpy matplotlib

Ejecuta los notebooks o scripts apuntando a tus imágenes en la carpeta /images.
