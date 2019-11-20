# 🔄 Complete, Remove, Repeat

En esta sección aprenderemos a completary remover nuestras tareas asi como a escuchar cuando el usuario realiza estas acciones. Para esta sección necesitaremos los conocimientos básicos de los metodos ``toggle`` asi como de ``classList`` y ``parentNode`` 

## 📚 Conceptos de está sección

El metodo ``toggle`` nos proporciona la capacidad de mostrar u ocultar elementos y contenido de nuestro sitio web. En este caso mostraremos y ocultaremos clases.

Usar ``classList`` es una forma práctica de acceder a la lista de clases de un elemento como una cadena de texto delimitada por espacios a través de element.className.

La propiedad de sólo lectura ``node.parentNode`` devuelve el padre del nodo. 

## ✔Completando una tarea
Para decirle a nuestra aplicación que se ha acompletado o removido una tarea, primero debemos crear las funciones de completado y de removido. Entonces creamos una función:

```js
function completeToDo(element) {
  
}
```
Luego, agregaremos los elementos que cambiaremos, en este caso, si una tarea es completada, queremos que el ícono del circulo cambie al igual que el texto, el cual ahora estará tachado. En caso de que el usuario quite el completado a la tarea, tambien queremos que cambie para mostrar que la tarea aún no ha sido completada, esto lo lograremos de la siguiente forma:

```js
function completeToDo(element) {
  element.classList.toggle(CHECK);
  element.classList.toggle(UNCHECK);
  element.parentNode.querySelector(".text").classList.toggle(LINE_THROUGH);
}
```

### getElementById
El metodo ``getElementById`` nos devuelve el elemento que contenga el id único (sensible a mayusculas) de nuestro documento. En este caso lo usaremos para obtener los elementos de la fecha, lista y nuestro input.

```js
const dateElement = document.getElementById("date");
const list = document.getElementById("lista");
const input = document.getElementById("input");
```

## 👀 Declarando clases
Como mencionamos anteriormente en el apartado de css y de html, declaramos ciertas clases y les dimos cierto diseño para poder usarlas posteriormente. Es en este momento donde declararemos estas clases en constanes para poder usarlas de una forma mas sencilla en el futuro. Esto se hace para no tener que escribir el nombre completo de la clase sino simplemente llamarla mediante una constante declarada. Las declararemos en mayusculas para diferenciarlas del resto. 

```js
const CHECK = "fa-check-circle";
const UNCHECK = "fa-circle-thin";
const LINE_THROUGH = "lineThrough";
```

## 📆 ¿Como mostramos la fecha?
Para mostrar la fecha de nuestro documento, necesitaremos llamar a la constante que declaramos arriba ``dateElement`` y usaremos su propiedad ``innerHTML``, esto lo igualaremos al metodo ``toLocaleDateString()`` que contendrá en sus parentesis dos propiedades ("Lugar y lengua de fecha", "opciones")

```js
dateElement.innerHTML = today.toLocaleDateString("es-US", options);
```

Declaremos arriba de este codigo una constante llamada ``options`` la cual contendrá las propiedades que mostrarán la forma en como se verá nuestra fecha. Estas propiedades son ``month``, ``day`` y ``weekday``, las cuales nos permitirán cambiar la forma en como se ve el mes, la fecha y el día respectivamente. 

```js
const options = { month:"short", day:"numeric", weekday:"long"};
```

Tambien declararemos una constante llamada ``today`` para almacenar dicha fecha. Ya habiendo terminado todo esto, nuestro código lucirá asi:

```js
const options = { month:"short", day:"numeric", weekday:"long"};
const today = new Date();

dateElement.innerHTML = today.toLocaleDateString("es-US", options);
```

## 👅 Resumen
Al final de cada paso para llegar a nuestra primera Aplicación Web, pondré un ejemplo de como debió quedar tu código para poder continuar con el taller ❤. Tu  documento ``js`` debe lucir de esta forma:

```js

//Select the elements
const clear = document.querySelector(".clear");
const dateElement = document.getElementById("date");
const list = document.getElementById("lista");
const input = document.getElementById("input");

//Classes names
const CHECK = "fa-check-circle";
const UNCHECK = "fa-circle-thin";
const LINE_THROUGH = "lineThrough";

// Mostrar fecha
const options = { month:"short", day:"numeric", weekday:"long"};
const today = new Date();

dateElement.innerHTML = today.toLocaleDateString("es-US", options);

```

## [Anterior](https://github.com/WorkshopTechnology/Materiales/blob/master/Talleres/CuentosDeJavascript/1.5.-comentariosVariables,prettyThings.md) - [Siguiente](https://github.com/WorkshopTechnology/Materiales/blob/master/Talleres/CuentosDeJavascript/4.-%20reusandoConFunciones.md)
