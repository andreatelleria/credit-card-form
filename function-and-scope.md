# Functions and scope

## Objetivo
Repasar conceptos de Javascript. Identificar el tipo de funciones, y el alcance de cada una de éstas, tomando como base el archivo app.js y la funcionalidad de este proyecto.
***

## Análisis estructural y lexical

### Funciones Globales
Funciones que no están dentro de una función y que automáticamente pasan a ser propiedades del objeto Window:

El evento ready está asociado a una función anónima, que crea un nuevo contexto de ejecución despúes de cargar todo el documento HTML y su DOM correspondiente.
```
  $(document).ready(function() {}
```

### Funciones Locales
Funciones que se encuentran dentro de otra función:

```
  $inputCard.on('input', function() {}) // Función anónima asociada al evento input
  function activeButton() {}
  function desactiveButton() {}
  function longitud(input) {}
  function soloNumeros(input) {}
  function isValidCreditCard(numberCard) {}
```

### Funciones Callback
Funciones que pasan como argumento en otra función:

Función soloNumeros, cuyo único parámetro es (input), recibe función longitud como argumento (valor de input).

```
  soloNumeros(longitud(numberCard));
```

### Function Statements
Funciones que siempre están disponibles incluso antes de haber sido definidas en el ambiente lexical:

```
  function activeButton() {}
  function desactiveButton() {}
  function longitud(input) {}
  function soloNumeros(input) {}
  function isValidCreditCard(numberCard) {}
```

### Function Expressions
Funciones que son definidas en una variable, por lo general anónimas, y que solo están disponibles después de haber sido declaradas en el ambiente lexical:

```
  var creditCardNumber = onlyNumbers(cardNumberLength(numberCard));
```

### Stack Execution o Pila de Ejecución
El contexto global de ejecución se crea por default. La pila de ejecución determina el orden en el que se ejecutarán las funciones. Recordemos que Javascript ejecuta comando por comando de manera síncrona.


### Event Loop o Bucle de Eventos
El bucle de eventos solo se empezará a ejecutar cuando la pila de funciones esté vacía. Como usuarios, solo podemos interactuar con un sitio web, através de los eventos, después que la página está levantada.