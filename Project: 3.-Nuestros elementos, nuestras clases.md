# 🧠 Comencemos con Javascript

En este momento comenzaremos con los pasos para elaborar el cerebro de nuestra aplicación web. 

## ✔ Seleccionar elementos
Primero debemos seleccionar que elementos de nuestro documento html necesitaremos para comenzar a trabajar. Para ello, utilizaremos la interfaz ``document`` para decirle a nuestro código que trabajaremos en el documento HTML al que esta vinculado. Tambien usaremos los metodos ``querySelector`` y ``getElementById``.

### querySelector
El metodo ``querySelector`` nos devuelve el primer elemento del documento (utilizando un recorrido ordenado de los nodos de nuestro documento) que coincida con el grupo especificado de selectores. En este caso, queremos que busque el elemento que tenga la clase ".clear".Y el elemento que nos devuelva lo guardamos en la constante ``clear``. 

```js
const clear = document.querySelector(".clear");
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

```

## [Anterior](https://github.com/WorkshopTechnology/Materiales/blob/master/Talleres/CuentosDeJavascript/1.5.-comentariosVariables,prettyThings.md) - [Siguiente](https://github.com/WorkshopTechnology/Materiales/blob/master/Talleres/CuentosDeJavascript/4.-%20reusandoConFunciones.md)
