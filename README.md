# Punto 1
## Paso 1: Activa el entorno virtual:

    source punto1/bin/activate


## Paso 2:

Corre el archivo de la siguiente manera:

    python3 main.py

## Paso 3:

El programa te pedirá que ingreses una expresión racional, por ejemplo:

Ingresa una expresión: (1/3 + 2/3)

El resultado se mostrará en formato de fracción simplificada.
Descripción del Código

El código está diseñado para:

    Lexer y Parser: Se generan a partir de una gramática en ANTLR que soporta las operaciones básicas (+, -, *, /) sobre números racionales.
    Evaluador: El archivo EvalVisitor.py implementa un visitante que recorre el árbol de análisis sintáctico y evalúa las expresiones racionales. Se asegura de manejar las fracciones, simplificarlas, y validar operaciones inválidas (como la división por 0).
    Simplificación de Fracciones: El evaluador utiliza el máximo común divisor (MCD) para simplificar los resultados de las operaciones con fracciones.

## Ejemplo

Si ingresas la expresión (1/3 + 2/3), el programa calculará el resultado como 3/3 y lo simplificará a 1/1.

    Ingresa una expresión: (1/3 + 2/3)
    1/1

Nota

El código maneja errores como la división por cero y verifica que las operaciones sean válidas antes de devolver un resultado


# Punto 2

## Activar el Entorno Virtual

Activa el entorno virtual de esta forma:

    
    source antlr-env/bin/activate




## Ejecutar el Código

Una vez configurado el entorno virtual, puedes ejecutar el código principal que procesa las expresiones MAP y FILTER. Para ello, utiliza el siguiente comando:


    python main.py

Entrada

El programa lee expresiones desde un archivo input.txt, que debe contener una o más líneas con expresiones de MAP o FILTER para procesar. Cada expresión debe estar en el formato adecuado.
Ejemplos de Entrada

el input es:



    MAP(lambda x: x + 1, [1, 2, 3])

    FILTER(lambda x: x % 2 == 0, [1, 2, 3, 4])


La salida será:


    Resultado MAP: [2, 3, 4]
    Resultado FILTER: [2, 4]

## Descripción del Código
El código se basa en una gramática desarrollada en ANTLR que permite procesar las funciones MAP y FILTER:

    MAP: Aplica una función a cada elemento de un iterable (como una lista) y devuelve una nueva lista con los resultados.
    FILTER: Filtra los elementos de un iterable basado en una función condicional, devolviendo una nueva colección con los elementos que cumplen la condición.

## Archivos Principales

    MapFunctionLexer.py y MapFunctionParser.py: Son generados por ANTLR a partir de la gramática. Estos archivos contienen el analizador léxico y sintáctico que se utiliza para procesar las expresiones.
    main.py: Archivo principal que lee el archivo input.txt, procesa las expresiones MAP y FILTER, y ejecuta las operaciones correspondientes.
    EvalVisitor.py: Implementa el recorrido del árbol sintáctico generado por ANTLR, aplicando las funciones de MAP y FILTER.
Nota

El código puede manejar operaciones aritméticas simples y condiciones de filtrado sobre los elementos de una lista, utilizando las funciones lambda definidas en el lenguaje de entrada.



# Punto 3
 
 ## Activar el Entorno Virtual

Como el entorno virtual ya está creado y configurado, solo necesitas activarlo.


    source punto3/bin/activate


## Ejecutar el Código

Una vez activado el entorno virtual, puedes ejecutar el código principal que procesa las expresiones de transformada de Laplace. Para ello, utiliza el siguiente comando:

    python main.py

Entrada

El programa lee expresiones desde un archivo input.txt, que debe contener una o más líneas con las funciones a transformar usando la sintaxis definida.

El archivo input.txt puede contener las siguientes líneas:


    Laplace(1)
    Laplace(e^a t)
    Laplace(t)
    Laplace(e^b t)

Estas funciones representan transformadas básicas, donde a y b son constantes en las funciones exponenciales.
Descripción del Código

El código se basa en una gramática desarrollada en ANTLR que permite calcular las transformadas de Laplace de funciones simples.


Archivos Principales

    LaplaceLexer.py y LaplaceParser.py: Son generados por ANTLR a partir de la gramática. Estos archivos contienen el analizador léxico y sintáctico que se utiliza para procesar las expresiones.
    main.py: Archivo principal que lee el archivo input.txt, procesa las expresiones y aplica la transformada de Laplace.
    Laplace.g4: Archivo de gramática utilizado por ANTLR para generar el lexer y el parser.

Ejecución del Código

El programa ejecuta las transformadas de Laplace para cada línea del archivo input.txt y las imprime en la consola.
Ejemplo de Salida

    Laplace(1)
    Laplace(e^a t)
    Laplace(t)
    Laplace(e^b t)

La salida será:

    
    Expresión: Laplace(1), Transformada: 1/s
    Expresión: Laplace(e^a t), Transformada: 1/(s - a)
    Expresión: Laplace(t), Transformada: 1/s^2
    Expresión: Laplace(e^b t), Transformada: 1/(s - b)

Nota

Este proyecto soporta transformadas básicas y se puede ampliar para manejar más funciones y expresiones complejas según las necesidades.
