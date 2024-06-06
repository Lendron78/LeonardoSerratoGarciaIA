Este codigo contiene código para implementar un modelo de red neuronal convolucional (CNN) utilizando TensorFlow/Keras. Este modelo se utiliza para predecir diferentes tipos de desastres a partir de imágenes de los desastres que se encuentran en el dataset.
En este proyecto se detectan:
- Asatos
- Incendios
- Robo casa habitación
- Tornados
- Inundaciones

# Importación de Librerías

Comienza importando varias librerías esenciales para el procesamiento de imágenes y la construcción del modelo de aprendizaje profundo


```python
import numpy as np
import matplotlib.pyplot as plt
from tensorflow.keras.models import load_model
from skimage.transform import resize
```

# Preparación de Datos de Imágenes

Se define una lista de nombres de archivos que contienen imágenes a ser procesadas. Se cargan y redimensionan estas imágenes a 28x28 píxeles, que es la entrada esperada por el modelo


```python
filenames = [
    'Downloads/Catastrofes/rurta de las imagenes',
]

images = []
for filepath in filenames:
    image = plt.imread(filepath)  # Carga la imagen en color
    image_resized = resize(image, (28, 28), anti_aliasing=True, clip=False, preserve_range=True)
    images.append(image_resized)

X = np.array(images, dtype=np.uint8)
test_X = X.astype('float32')
test_X = test_X / 255.0  # Normalización de las imágenes

```

# Predicción

Las imágenes preprocesadas se pasan a través del modelo para hacer predicciones. El modelo predice una clase de riesgo para cada imagen


```python
predicted_classes = risk_model.predict(test_X)
```

Se define una lista con las posibles clases que el modelo puede predecir


```python
risk = ['asalto', 'incendio', 'inundacion', 'robo', 'tornado']
```

Se itera sobre las predicciones y se muestran las imágenes originales junto con la predicción correspondiente


```python
for i, img_tagged in enumerate(predicted_classes):
    original_image = plt.imread(filenames[i])  # Carga la imagen original
    plt.imshow(original_image)
    plt.title(f"Predicción: {risk[img_tagged.tolist().index(max(img_tagged))]}")
    plt.axis('off')  # Oculta los ejes
    plt.show()

    print(filenames[i], risk[img_tagged.tolist().index(max(img_tagged))])
```

Este proceso es útil para tareas de clasificación de imágenes en el contexto de desastres naturales o incidentes, proporcionando una herramienta potencialmente valiosa para análisis rápidos y eficientes.
