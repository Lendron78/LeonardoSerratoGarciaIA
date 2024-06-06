# Descripcion
El juego combina elementos tradicionales de un juego 2D con el uso de una red neuronal para el control automático del jugador, permitiendo la recopilación de datos de entrenamiento durante el juego manual y el uso de estos datos para entrenar la red neuronal para el juego automático.

# Definición de Dimensiones y Variables
Se definen las dimensiones del juego (w y h), y varias variables globales para manejar los elementos del juego, el control del jugador, y las funcionalidades relacionadas con la red neuronal:

- jugador, fondo, bala: Representan los sprites del jugador, fondo y la bala respectivamente.
- cursors, menu: Para manejar las entradas del teclado y el menú.
- nnNetwork, nnTrainer, nnOutput, trainingData: Para manejar la red neuronal y los datos de entrenamiento.
- autoMode, trainingComplete, trainingGames, currentGame, PX, PY, REVERTIRV, REVERTIRH: Variables de control para el modo automático y el entrenamiento.


# Funciones principales
- preload(): Precarga los activos necesarios del juego.
- create(): Configura el juego, inicializa elementos y crea la red neuronal.
- update(): Se ejecuta en cada frame, manejando el movimiento del jugador y la detección de colisiones.
- setRandomBalaVelocity(): Establece una velocidad aleatoria a la bala.
- manejarMovimientoManual(): Maneja el movimiento del jugador basado en las entradas del teclado y registra los datos de entrenamiento.
- manejarMovimientoAutomatico(): Controla el movimiento del jugador utilizando la salida de la red neuronal.
- registrarDatosEntrenamiento(): Registra los datos de entrenamiento cuando el modo automático está desactivado.
- colisionar(): Se ejecuta cuando hay una colisión entre la bala y el jugador, activando el modo automático y pausando el juego.
- pausar(): Pausa el juego y muestra el menú de pausa.
- manejarPausa(event): Maneja las entradas del menú de pausa para reanudar el juego o iniciar el entrenamiento de la red neuronal.

# Logica

1 Control Manual del Jugador:
- El jugador puede moverse hacia arriba, abajo, izquierda y derecha utilizando las teclas de flecha del teclado.
- El movimiento del jugador se registra y se utilizan estos datos para el entrenamiento de la red neuronal cuando está activado el modo automático.
    
2 Control Automático del Jugador:
- Cuando la bala y el jugador colisionan, el juego entra en modo automático.
- En el modo automático, el movimiento del jugador se determina utilizando una red neuronal.
- La red neuronal toma como entrada la posición relativa de la bala con respecto al jugador y emite comandos de movimiento para el jugador.

3 Entrenamiento de la Red Neuronal:
- Durante el juego manual, se recopilan datos de entrenamiento registrando la posición relativa de la bala y los movimientos del jugador.
- Estos datos se utilizan para entrenar la red neuronal, lo que permite al jugador moverse automáticamente para esquivar la bala en futuros juegos.

4 Interfaz de Usuario:
- El juego tiene una función de pausa que muestra un menú cuando se hace clic en la pantalla.
- Desde el menú de pausa, el jugador puede reiniciar el juego y borrar los datos de entrenamiento o entrenar la red neuronal con los datos recopilados.

5 Colisión:
- Cuando la bala y el jugador colisionan, se activa el modo automático y se pausa el juego.
- Esto indica que el jugador ha sido alcanzado por la bala y la red neuronal debe intentar evitarlo en futuros juegos.



```python

```
