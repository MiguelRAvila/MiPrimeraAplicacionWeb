# 📦 Guardando en el storage
Este es el último paso de nuestra aplicación web, aquí guardaremos nuestra información para que cuando recarguemos la página, nuestras tareas sigan ahi!

## 🤗 Conceptos
### 🤔 ¿LocalStorage?
Cuando se desarrolla una aplicación compleja, es muy habitual utilizar una y otra vez las mismas instrucciones. Para ello se crearon las funciones, las cuales son un conjunto de instrucciones que se agrupan para realizar una tarea concreta y que se pueden reutilizar fácilmente. 

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

## ✏ Apliquemos los conceptos de localStorage
### 🔀Cambiemos las variables (again)
Lo primero que debemos hacer es modificar la forma en la que declaramos las variables ``LISTA`` e ``Id`` en la sección de Variables. Esto es porque al momento de recuperar las tareas que no hemos eliminado, necesitaremos que estos valores no sean declarados en cero, sino solamente existan sin ningun valor dentro. 

```js
//Variables

let LIST, id;
```

### 💻Añadir tareas a nuestro almacenamiento local
Para lograr añadir los datos a nuestro almacenamiento local, usaremos el ``localStorage`` con su función ``setItem`` para añadir estos valores al almacenamiento local. Ahora, para especificar en donde y a que variable se agregaran, modificaremos las propiedades "key" y el "value" que queremos almacenar. Además, usaremos el método ``JSON.stringify()`` para convertir nuestra LISTA en un string. (NOTA ROJA: Este código lo debemos colocar en todas las secciones donde la variable objeto LISTA se vea modificada

```js
localStorage.setItem("TODO", JSON.stringify(LIST)); 
```
En este caso, nosotros actualizamos la LISTA en dos puntos:

```js
//Escuchar Enter
document.addEventListener("keyup", function (event) {
    if (event.keyCode == 13) {
        const toDo = input.value;
        //Si el input no está vacio
        if (toDo) {
            addToDo(toDo, id, false, false);
            LIST.push({
                name: toDo,
                id: id,
                done: false,
                trash: false,
            });
            // Añadir items al almacenamiento local
            localStorage.setItem("TODO", JSON.stringify(LIST));
            id++;
        }
        input.value = "";
    }
});
// Target elements

list.addEventListener("click", function (event) {
    const element = event.target;
    const elementJob = element.attributes.job.value;

    if (elementJob == "complete") {
        completeToDo(element);
    } else if (elementJob == "delete") {
        removeToDo(element);
    }

    // Añadir items al almacenamiento local
    localStorage.setItem("TODO", JSON.stringify(LIST));
});
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

