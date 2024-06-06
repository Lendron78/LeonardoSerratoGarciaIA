# Descripcion
En estre proyecto se usaron imagenes donde aparecian imagenes de Willy (positivas) e imagenes donde no se encontraba Wally (Negativas).
Para poder hacer un xml, se uso Cascade Trainer GUI, el cual nos ayuda a tomar en cuenta las imagenes negativas y positivas, tomando en cuenta un porcentaje para tomar como buenas, toma en consideracion el tamaño de las imagenes si una esta diferente el entrenamiento no funcionara como debe. Una vez agregado las imagenes y el entrenamiento este concluido se crea el xml que usaremos para encontrar a Wally.

# Se carga la imagen 


```python
image = cv.imread(r'ruta donde esta la imagen')
```

# Hace la escala de grises


```python
gray = cv.cvtColor(image, cv.COLOR_BGR2GRAY)
```

# Se carga el clasificador.xml


```python
wally = cv.CascadeClassifier(r'cascade.xml')
```

# Se detecta Wally


```python
wally_detections = wally.detectMultiScale(gray, scaleFactor=1.11, minNeighbors=8, minSize=(50,50))
```

# Se muestra la imagen idicando donde esta


```python
for (x, y, w, h) in wally_detections:
    cv.rectangle(image, (x, y), (x + w, y + h), (0, 255, 0), 2)
    cv.putText(image, 'Wally', (x, y - 10), cv.FONT_HERSHEY_SIMPLEX, 0.9, (0, 255, 0), 2)

# Muestra el resultado
cv.imshow('Donde esta Wally?', image)
cv.waitKey(0)
cv.destroyAllWindows()
```

# Conclusion
Los parametros FactorScale, minSize, minNeighbors, nos ayudan para encontrar a wally.
Para encontrar a Wally a veces hay que jugar un poco con estos factores y asi poder encontrarlo, se tiene que jugar con los valores hasta encontrar a wally.


```python

```
