# Functions y scope

En el siguiente contenido se identificaran las funciones globales, locales, funciones de callback, function expressions, contextos de ejecución, function statements, scope closure, qué funciones forman parte de la pila de ejecución y qué funciones forman parte de la cola de eventos.

## Funciones globales

> Son las funciones que no se encuentran dentro de otra función.

Por ejemplo, `$(document).ready()`, sería la única función global, ya que no se encuentra dentro de ninguna funcion.

## Funciones locales

> Por ejemplo, dentro del scope de la funcion `$(document).ready()` se encuentran las siguientes funciones:

- `activeButton()`
- `desactivButton()`
- `longitud(input)`
- `soloNumeros(input)`
- `isValidCreditCard(numberCard)`

## Variables globales;

```js
var $buttonNext = $('#next');
```

## Variables Locales:

```js
var regex = /^[0-9]+$/;
var creditCardNumber = soloNumeros(longitud(numberCard));
var arr = [];
var sumaTotal = 0;
```

## Function expression

> Da el resultado de una función como expresión a la variable y tambien puede ser llamada a través de esa variable.

```js
// Ejemplo
var greet = function() {
  return 'Hello world';
};
```

## Function statements

> Cuando llamas a la funcion antes de crearla.

```js
// Ejemplo
hello();

function hello() {
  console.log('hola mundo');
}
```

## Closure

> Un closure es un tipo especial de objeto que combina dos cosas: una función, y el entorno en que se creó esa función.

```js
// Ejemplo
function inicia() {
  var nombre = "Mozilla"; // 'nombre' es una variable local creada por la función 'inicia'
  function muestraNombre() { // 'muestraNombre' es una función interna (un closure)
    alert(nombre); // dentro de esta función usamos una variable declarada en la función padre
  }
  muestraNombre();
}
inicia();
```

## Execution stack

- `console.log()`
- `$(document).ready()`

## Funciones de callback:

```js
function longitud(input) {
  if (input.trim().length === 16) {
    return input;
  }
}

function soloNumeros(input) {
  var regex = /^[0-9]+$/;
  if (regex.test(input)) {
    return input;
  }
}
```