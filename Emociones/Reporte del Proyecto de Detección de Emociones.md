# Descripcion
Este proyecto utiliza OpenCV para procesar imágenes y detectar emociones a través del reconocimiento facial. El flujo del proyecto abarca desde la preparación del conjunto de datos hasta la implementación de un sistema en tiempo real para la detección de emociones utilizando una cámara.

# Importación de Bibliotecas

Se importan las siguientes bibliotecas necesarias:
- OpenCV (cv2): Para el procesamiento de imágenes y video.
- NumPy (numpy): Para la manipulación de matrices.
- OS (os): Para la manipulación de archivos y directorios.

# Etiquetado y Lectura de Imágenes
El código recorre cada carpeta de emociones y, dentro de cada carpeta, recorre cada archivo de imagen, agregando la etiqueta correspondiente y los datos de la imagen a las listas respectivas. La etiqueta asignada corresponde a la carpeta de la emoción a la que pertenece la imagen.

# Entrenamiento del Modelo
Se crea un objeto LBPHFaceRecognizer, se entrena con los datos de las imágenes y etiquetas, y se guarda el modelo entrenado en un archivo XML.


# Conclucion
Este proyecto demuestra el uso de técnicas de procesamiento de imágenes y aprendizaje automático para la detección y reconocimiento de emociones en tiempo real. Utilizando OpenCV, se logra capturar, procesar y clasificar rostros desde una cámara web, aplicando un modelo entrenado previamente para identificar diferentes emociones.


```python

```
