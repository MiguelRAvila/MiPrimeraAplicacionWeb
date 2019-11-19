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

### 📏 Maquetemos
Debemos tener muy en cuenta cual es el contenido de nuestra aplicación web y como podemos maquetarla para que podamos añadirle estilos y posteriormente darle funcionalidad con Javascript. Esto lo haremos en el ``<body>`` y usaremos las siguientes etiquetas:

```html
<div class="contenedor">
        <div class="header">

        </div>
        <div class="contenido">
            <ul id="lista">
              
            </ul>
        </div>
        <div class="add-item">

        </div>
    </div>
```
### 📐 ¿Header?
Dentro del header colocaremos otro ``div`` para que contenga nuestro ícono de reinicio así como otro ``div`` para contener la fecha de nuestra lista.

```html
        <div class="header">
            <div class="clear">
                <i class="fa fa-refresh"></i>
            </div>
            <div id="date"></div>
        </div>
```
### 📃 Nuestro contenido: la lista
En nuestro contenido, más especificamente, dentro de nuestra ``ul`` con una id de "lista" escribiremos un item de ejemplo para que podamos guiarnos y más tarde lo diseñemos de la mejor forma posible. 

```html
        <div class="contenedor">
            <ul id="lista">
                <li class="item">
                    <i class="fa fa-circle-thin co" job="complete" id="0"></i>
                    <p class="text">Tomar un café</p>
                    <i class="fa fa-trash-o de" job="delete" id="0"></i>
                </li>
            </ul>
        </div>
```
### 📎 ¿Dónde añadimos un elemento a la lista?
Dentro de nuestro ``div`` con clase "add-item" encontraremos el ícono de añadir una nueva tarea a la lista, así como un ``input`` para que el usuario ingrese su tarea. 

```html
        <div class="add-item">
            <i class="fa fa-plus-circle"></i>
            <input type="text" id="input" placeholder="Añadir una tarea">
        </div>
```

## 👅 Resumen
Al final de cada paso para llegar a nuestra primera Aplicación Web, pondré un ejemplo de como debió quedar tu código para poder continuar con el taller ❤. Tu ``HTML`` debe lucir de esta forma:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>To Do List</title>
</head>
<body>
    <div class="contenedor">
        <div class="header">
            <div class="clear">
                <i class="fa fa-refresh"></i>
            </div>
            <div id="date"></div>
        </div>
        <div class="contenido">
            <ul id="lista">
                <!-- <li class="item">
                    <i class="fa fa-circle-thin co" job="complete" id="0"></i>
                    <p class="text">Beber Café</p>
                    <i class="fa fa-trash-o de" job="delete" id="0"></i>
                </li> -->
            </ul>
        </div>
        <div class="add-item">
            <i class="fa fa-plus-circle"></i>
            <input type="text" id="input" placeholder="Añadir una tarea">
        </div>
    </div>
</body>
</html>
```

## [Anterior](https://github.com/WorkshopTechnology/Materiales/blob/master/Talleres/CuentosDeJavascript/1.5.-comentariosVariables,prettyThings.md) - [Siguiente](https://github.com/WorkshopTechnology/Materiales/blob/master/Talleres/CuentosDeJavascript/4.-%20reusandoConFunciones.md)
