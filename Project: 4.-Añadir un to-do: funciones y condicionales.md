# ⭕ La función To Do

A lo largo de esta siguiente parte de nuestro taller veremos que para lograr añadir nuevos elementos necesitaremos conocimientos las funciones, condicionales, y el metodo insertAdjacentHTML. Para que al momento de teclear ENTER en nuestro teclado se añada una nueva funcion, necesitaremos otros conocimientos como son el metodo addEventListener.
## 🤗 Conceptos
### 👀 ¿Qué es una función?
Cuando se desarrolla una aplicación compleja, es muy habitual utilizar una y otra vez las mismas instrucciones. Para ello se crearon las funciones, las cuales son un conjunto de instrucciones que se agrupan para realizar una tarea concreta y que se pueden reutilizar fácilmente. 

La mayor parte de las funciones no necesitan de ningun tipo de información extra, pero en las aplicaciones reales estas necesitan de variables llamadas argumentos. Estos argumentos se indican dentro de parentesis al lado del nombre de la función y se separan con una coma.

Por ejemplo, en una funcion sencilla que quiere sumar dos numeros:

```js
//Definimos la función
function suma(numeroa, numerob) {
  var resultado = numeroa + numerob;
  alert("El resultado es " + resultado);
}

//Declaramos los numeros que queremos que sume
var numeroa = 3;
var numerob = 4;

//Llamamos a la funcion para que imprima el resultado
suma(numeroa, numerob);
```

### 🔀 Condiciones 
En las condiciones, como en cualquier otro lenguaje de programación verifica si una condición se cumple como verdadera, en caso de serlo, ejecuta una sentencia y en caso contrario ejecuta otra (o no hace absolutamente nada).

```js
if(condicion1) {
  sentencia1
} else {
  sentencia1.1
}
```
Otra forma de sintaxis es 

```js
const name = parametro ? option1 : option2;
```
### ✂ insertAdjacentHTML
Este metodo nos ayudará para insertar una nueva tarea en nuestra aplicacion web. Funciona mediante el uso de dos propiedades ``position`` y ``text``. En la primera indicamos en que parte del documento queremos añadir el texto HTML ( beforebegin, afterbegin, beforeend, afterend ). Y en el text, escribimos que es lo que deseamos agregar a nuestro documento

```js
element.insertAdjacentHTML(position, text);
```
## 🤓 Hora de aplicar los conceptos

### Nuestra funcion addToDo
Primero debemos definir nuestra función ``addToDo`` para hacer nuestro trabajo más sencillo. Esta funcion usara (de momento) el parametro ``toDo`` para funcionar, el cual será el texto de nuestra tarea.

```js
function addToDo(toDo){
  
}
```

Luego de esto, creamos dentro de la función, nuestro ``insertAdjacentHTML``

```js
function addToDo(toDo){
   
   list.insertAdjacentHTML(position, item);
}
```
Entonces, te darás cuenta de que no tenemos declarados ni ``position`` ni ``item`` entonces los agregaremos arriba. 

La constante ``item`` equivale al ejemplo que colocamos anteriormente en nuestro HTML con algunos cambios ligeros.

```js
    const item = `

    <li class="item">
        <i class="fa fa-circle-thin co" job="complete" id="0"></i>
        <p class="text">${toDo}</p>
        <i class="fa fa-trash-o de" job="delete" id="0"></i>
    </li>

    `;
```
Mientras que la constante ``position`` tendrá el valor "beforeend" para que cada vez que añadamos una tarea, se agregue hasta el final.


```js
  const position = "beforeend";
```

De esta forma, nuestra funcion (de momento) lucirá de esta forma:


```js
function addToDo(toDo){

     const item = `

     <li class="item">
          <i class="fa fa-circle-thin co" job="complete" id="0"></i>
          <p class="text">${toDo}</p>
          <i class="fa fa-trash-o de" job="delete" id="0"></i>
     </li>

     `;
    
    const position = "beforeend";
    
   list.insertAdjacentHTML(position, item);
}
```

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
