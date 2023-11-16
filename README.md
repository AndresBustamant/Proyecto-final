# Proyecto-final

![ideogram (1)](https://github.com/jeriosv/taller_1/assets/142249529/5bd59e64-9074-4caf-beac-929549df998f)


Integrantes del equipo:
- Andrés Camilo Bustamante Guzmán
- Jhonatan Esteban Forero Velásquez
- Jaime Eduardo Ríos Villegas
  
**Ahorcado**

planteamiento previo

1. creacion de la base de datos
   para esta parte se crea un archivo de texto con las palabras  que van a estar presentes en el juego, claro esta que se tienen que clasificar con el fin de generar los tres niveles de dificultad

![base de datos](https://github.com/AndresBustamant/Proyecto-final/assets/141858005/b9b88b1b-f72b-4587-8d7f-9de5e6706d8f)

   
2. planteamiento del nivel del juego
    En este punto se a partir de la clasificacion de las palabras del punto anterior y tomando en cuenta la decicion o lo que quiere el jugador se podra elegir entre tres niveles regidos por la extension de las palabras

![dificultad](https://github.com/AndresBustamant/Proyecto-final/assets/141858005/dc4cff37-20f6-4aed-8c1f-ba551ddbb221)

3. inicio del juego
   a partir de la lista de palabras y el uso de la funcion random, se va a seleccionar una palabra oculta con la que el jugador va a interactuar

   "palabra_aleatoria=random.choice(listadepalabras)"
   
4. evaluacion palabra o letra
   posteriormente se crea un ciclo con el cual se evaluara la pertenencia de las letras a la palabra oculta, teneiendo en cuenta dos condiciones primero como es la entrada ya que si es una letra se compara la pertenencia a la palabra y si es palabra e evalua que sea igual; la segunda condicion radica en la no repeticion de la letra 

5. entorno 
   para el entorno se tiene en cuenta dos partes: la primera corresponde a el tablero, donde se mostraran las palabras acertadas y el segundo es el  dibujo de hagman, para este a partir de la delimiticacion de un numero de intentis disponibles se dispondra el desarrollo del dibujo de hagman, el cual va evolucionando o completandose a parir de los intentos erroneos.

![imagen ](https://github.com/AndresBustamant/Proyecto-final/assets/141858005/99d5b9d0-84b2-4659-8f07-9b79415653a5)


Flujograma del programa

```mermaid
  graph TD;
    A(INICIO) --> B{Seleccionar el nivel de dificultad}
    B -->|4 y 5 letras| D[Fácil] 
    B -->|6 y 7 letras| E[Intermedio] 
    B -->|8 o más letras| F[Difícil] 
    D --> G[Generar palabra aleatoria] --> H[Ingreso del usuario]
    H --> M{Ingresó o terminó la palabra correcta}
    E --> G 
    F --> G 
    H --> I{La letra está en la palabra}
    I -->|Sí| J[Acertó letra]
    I -->|No| K[Falló letra]
    K --> L(Mostrar gráfico ahorcado)
    J --> L
    J --> H
    L --> H
    M --> |Sí| N[Ganaste] --> P(FIN)
    M --> |No| O[Continua] 
    O --> L
```
