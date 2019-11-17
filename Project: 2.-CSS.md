# 💅 And play harder

<p align="center">
  <img  src="https://github.com/MiguelRAvila/MiPrimeraAplicacionWeb/blob/master/image5.png">
</p>

## 🎨 ¡Ahora el diseño!
Para que la aplicación web se vea como la presentamos originalmente, debemos trabajar con un archivo de ``css`` para cambiar y mejorar los diseños. Primero cambiaremos el ``body``, para ello escribiremos la etiqueta "body" completa y realizaremos los siguientes cambios:

* El ``padding`` y el ``margin`` será de 0
* Su ``font-family`` será la que descargamos con Google Fonts

```css
body{
    padding: 0;
    margin: 0;
    background-color: rgba(0,0,0,0.1);
    font-family: 'Titillium Web', sans-serif;
}
```
### 📏 Hora de diseñar clases
Para poder añadir un diseño css a una clase, se usa el ``.`` antes del nombre de la clase para poder modificar su diseño. Primero haremos cambios al contenedor con la etiqueta ``.contenedor``.

* El ``padding`` es de 10px
* Su ``width`` será de 380px, para darle un valor absoluto de ancho
* Su ``margin`` tiene un valor nulo y ``auto``, para centrar nuestra aplicación.

```css
.contenedor{
    padding:10px;
    width:380px;
    margin:0 auto;
}
```
### 📐 Diseñemos el Header
El ``header`` contiene muchos cambios en cuanto a su diseño.


* El ``width`` es de 380px para definir su ancho.
* Su ``height`` es de 200px para que tenga el largo que vemos en el diseño original
* Su ``background-image`` tendrá una ``url`` que lo vincule directamente a la imagen que queramos ponerle a nuestra lista
* Otras propiedades como el ``background-size`` y el ``background-repeat`` se usan para brindarle unas caracteristicas adicionales como el tamaño de 100% 200% para ajustarlo al tamaño del Header, o para decirle a nuestro diseño que no queremos que ese fondo se repita para rellenar el espacio donde se encuentra.
* El ``border-radius`` se usa para dotar de un borde redondeado al header, usaremos 15px 15px 0 0 para darle un borde redondeado solo a los extremos superiores.
* La ``position`` tendrá un valor "relative" para que se mantenga dentro de nuestro contenedor

```css
.header{
    width: 380px;
    height:200px;
    background-image: url('../img/bg2.jpg');
    background-size: 100% 200%;
    background-repeat: no-repeat;
    border-radius: 15px 15px 0 0;
    position: relative;
}
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
