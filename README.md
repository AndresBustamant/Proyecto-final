# Proyecto Final: Ahorcado


![ideogram](https://github.com/AndresBustamant/Proyecto-final/assets/142249529/de4dfc43-0355-4ac5-a1c8-85d12fcd6e70)


Integrantes del equipo:
- Andrés Camilo Bustamante Guzmán
- Jaime Eduardo Ríos Villegas
  
**Ahorcado**

Planteamiento previo

1. Creación de la base de datos
   para empezar se acude a buscar palabras en español con el fin de trabajarlas y traducirlas a otros idiomas (inglés y francés), en este caso se trabajó a partir de 1102 palabras las cuales después de tratarlas se modificaron de tal manera que se adaptaran a los otros idiomas implementados.

Ejemplo de las palabras:


![base de datos](https://github.com/AndresBustamant/Proyecto-final/assets/141858005/b9b88b1b-f72b-4587-8d7f-9de5e6706d8f)

   
2. Planteamiento del nivel del juego

   En este punto, a partir de la clasificación de las palabras del punto anterior y tomando en cuenta la decisión o lo que quiere el jugador se podrá elegir entre tres niveles regidos por la extension de las palabras (palabras de 1-5, de 5-8 y de 8 en adelante)

![dificultad](https://github.com/AndresBustamant/Proyecto-final/assets/141858005/dc4cff37-20f6-4aed-8c1f-ba551ddbb221)

3. Inicio del juego
   a partir de la lista de palabras y el uso de la función random, se va a seleccionar una palabra oculta con la que el jugador va a interactuar

   "random.randint(0, len(lista_palabras) - 1))"
   
4. Evaluación palabra o letra
   posteriormente se crea un ciclo con el cual se evaluará la pertenencia de las letras a la palabra oculta, teniendo en cuenta la pertenencia de cada letra a la palabra, dando como resultado el reemplazo de la letra si es True o dejar el espacio sin alterar si es false.

5. Entorno 
   para el entorno se tiene en cuenta dos partes: la primera corresponde a el tablero, donde se mostraran las palabras acertadas y el segundo es el dibujo de hagman, para este a partir de la delimitación de un número de intentos disponibles se dispondrá el desarrollo del dibujo de hangman, el cual va evolucionando o completándose a partir de los intentos erróneos.

![imagen ](https://github.com/AndresBustamant/Proyecto-final/assets/141858005/99d5b9d0-84b2-4659-8f07-9b79415653a5)

6.  Requerimientos:
  el programa en si no necesita mucho ya que sus palabras ya estan apropiadas como un string, lo que si es necesario es instalar pyfiglet para poder evidenciar la victoria de una manera mas satisfactoria.

  
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
