# Descripcion
Este juego es un juego de plataformas en el que el jugador controla un personaje llamado que puede moverse horizontalmente y saltar para esquivar balas disparadas desde diferentes direcciones. 

# Definición de Dimensiones y Variables
Se definen las dimensiones del juego (w y h), y varias variables globales para manejar los elementos del juego, el control del jugador, y las funcionalidades relacionadas con la red neuronal:

- jugador: Objeto que representa al personaje controlado por el jugador.
- fondo: Imagen de fondo del juego.
- nave, nave2, nave3: Objetos que representan naves enemigas.
- bala, bala2, bala3: Objetos que representan balas disparadas por las naves enemigas.
- salto: Tecla utilizada para que el jugador realice un salto.
- avanza: Tecla utilizada para mover al jugador hacia la derecha.
- menu: Menú de pausa del juego.
- velocidadBala, velocidadBala2, velocidadBala3: Velocidades de las balas.
- despBala, despBala2, despBala3: Distancias entre el jugador y las balas enemigas en diferentes momentos.
- estatusAire, estatuSuelo, estatusDerecha, estatusIzquierda: Variables que indican el estado del jugador (en el aire, en el -suelo, moviéndose hacia la derecha o hacia la izquierda).
- modoAuto: Variable que indica si el juego está en modo automático o no.
- eCompleto: Variable que indica si el proceso de entrenamiento de la red neuronal está completo.
- datosEntrenamiento: Datos utilizados para entrenar la red neuronal.
- nnNetwork, nnEntrenamiento, nnSalida: Variables relacionadas con la red neuronal.

# Funciones
- Variables Globales: Se definen varias variables para el tamaño del juego, los elementos del juego (jugador, fondo, balas, etc.), velocidades, estado del juego, y una red neuronal para el modo automático.

- Funciones de Precarga (preload): Se cargan las imágenes y sprites necesarios para el juego, como el fondo, los personajes, las naves y las balas.

- Función de Creación (create): Se inicia el sistema de físicas del juego, se configuran las propiedades de los elementos del juego, se establecen eventos de teclado para controlar al jugador y se crea una instancia de la red neuronal.

- Funciones de Lógica del Juego (update): Esta es la función principal del juego que se ejecuta continuamente. Aquí se manejan colisiones, se actualiza el estado del jugador y de las balas, se controla el movimiento del jugador, y se activa el modo automático si está habilitado.

- Funciones de Disparo: Hay tres funciones (disparo, disparo2, disparo3) para el lanzamiento de balas, cada una con diferentes velocidades y direcciones.

- Funciones de Pausa: Las funciones pausa y mPausa controlan la pausa del juego y la interacción con el menú de pausa.

- Funciones Auxiliares: Hay varias funciones auxiliares como resetVariables, resetPlayer, saltar, etc., que ayudan en la manipulación de variables y acciones del jugador.

- Funciones de Redes Neuronales: Se definen funciones relacionadas con la red neuronal como enRedNeural, datosDeEntrenamiento, EntrenamientoSalto, que se utilizan para entrenar y hacer predicciones en el modo automático del juego.

# Logica
1 Inicialización del Juego:
- Se configuran las dimensiones del juego y se cargan los assets necesarios, como imágenes y sprites.
- Se inicializa el motor de física y se establece la gravedad.

2 Creación de Elementos:
- Se crean el fondo, el jugador, las naves enemigas y las balas.
- Se habilita la física para el jugador y las balas, y se establece la detección de colisiones entre ellos.

3 Control del Jugador:
- Se permite al jugador moverse hacia la derecha y saltar utilizando el teclado.
- Se limita el movimiento del jugador dentro de los límites establecidos y se ajusta su velocidad de acuerdo con la acción realizada.

4 Control Automático:
- Se implementa una lógica de control automático utilizando una red neuronal.
- La red neuronal toma datos de entrada basados en la posición y velocidad de las balas, así como del estado del jugador (en el suelo o en el aire).
- La red neuronal decide si el jugador debe saltar, moverse hacia adelante, o detenerse basándose en estos datos.

5 Entrenamiento de la Red Neuronal:
- Durante el juego manual, se recopilan datos de entrenamiento que incluyen la posición y velocidad de las balas, así como el estado del jugador.
- Estos datos se utilizan para entrenar la red neuronal, lo que le permite tomar decisiones más precisas durante el juego automático.

6 Interfaz de Usuario:
- Se implementa una función de pausa que muestra un menú cuando se hace clic en la pantalla.
- Desde el menú de pausa, el jugador puede reiniciar el juego y borrar los datos de entrenamiento o activar el modo automático.

7 Actualización del Juego:
- Se actualiza continuamente el estado del juego, incluyendo la posición de los elementos, la detección de colisiones y la lógica de control del jugador.
