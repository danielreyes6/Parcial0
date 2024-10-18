#Punto 1
Paso 1: Activa el entorno virtual:

    source venv/bin/activate

Paso 2:

Corre el archivo de la siguiente manera:

    python3 main.py

    
El programa te pedirá que ingreses una expresión racional, por ejemplo:

Ingresa una expresión: (1/3 + 2/3)

El resultado se mostrará en formato de fracción simplificada.
Descripción del Código

El código está diseñado para:

    Lexer y Parser: Se generan a partir de una gramática en ANTLR que soporta las operaciones básicas (+, -, *, /) sobre números racionales.
    Evaluador: El archivo EvalVisitor.py implementa un visitante que recorre el árbol de análisis sintáctico y evalúa las expresiones racionales. Se asegura de manejar las fracciones, simplificarlas, y validar operaciones inválidas (como la división por 0).
    Simplificación de Fracciones: El evaluador utiliza el máximo común divisor (MCD) para simplificar los resultados de las operaciones con fracciones.

Ejemplo

Si ingresas la expresión (1/3 + 2/3), el programa calculará el resultado como 3/3 y lo simplificará a 1/1.

    Ingresa una expresión: (1/3 + 2/3)
    1/1

Nota

El código maneja errores como la división por cero y verifica que las operaciones sean válidas antes de devolver un resultado
