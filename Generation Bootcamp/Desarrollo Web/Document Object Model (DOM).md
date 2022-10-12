---
title: Document Object Model (DOM)
updated: 2022-08-15 04:07:10Z
created: 2022-08-09 03:40:47Z
tags:
  - front-end
  - javascript
---

# Document Object Model (DOM)

[toc]

* * *

El Modelo de Objetos de Documento (*DOM*) es la representación de los objetos que conforman la estructura y el contenido de un documento en la web. Cualquier documento HTML es una estructura de árbol y la estructura de la página se llama **árbol DOM**.

El **HTML DOM** es un estándar sobre cómo obtener, cambiar, agregar o eliminar elementos HTML. Este estándar también es una ***API*** (Interfaz de programación) para JavaScript.

La interfaz **Window** representa una ventana que contiene un documento DOM; la propiedad del documento apunta al documento DOM cargado en esa ventana. JavaScript accede al DOM a través de la interfaz de **Document**. Este objeto representa cualquier página web cargada en el navegador y sirve como un punto de entrada al contenido de una página web.

Un **nodo** es una clase abstracta en la que se basan los objetos en el DOM. Todo en HTML es un nodo, esto incluye el documento, los elementos HTML, el texto en los elementos, los atributos y los comentarios.

### Métodos del DOM

Los nodos en el DOM pueden ser creados, modificados y eliminados mediante métodos.

#### Métodos para la selección de elementos en el DOM

- **getElementById(*id*)**: Buscar el elemento HTYML con el id indicado.

```js
const parrafo1 = document.getElementById('parrafo1');  // Obtiene el elemento con el id 'parrafo1' y se lo asigna a la variable 'parrafo1'
```

- **querySelector(*selector*)**: Buscar la primera coincidencia del selector indicado.

```js
const parrafo2 = document.querySelector(".parrafo");  // Selecciona el primer elemento con la clase 'parrafo'
```

- **querySelectorALL(selector)**: Devuelve una lista de nodos conteniendo todas las coincidencias del selector indicado.

```js
const parrafos = document.querySelectorAll('p');  //Selecciona todos los elementos de tipo <p>
```

Es importante mencionar que **una lista de nodos no es un arreglo**, por lo tanto, no puede usar métodos para arreglos. Para convertir la lista en un arreglo, puede utilizarse `Array.from()`

#### Métodos para crear elementos en el DOM

- **document.createElement(*etiqueta*, *\[opciones\]*)**: Crea un elemento HTML definido por la etiqueta indicada.

```js
const imagen = document.createElement('img');  // Crea un elemento de tipo <img> y se lo asigna a la variable 'imagen'
```

- **createComment(*texto*)**: Crear y devuelve un nodo de comentarios.
- **createTextNode(*texto*)**: Crea y devuelve un nodo HTML con el texto indicado.
- **cloneNode(*deep*)**: Clona el nodo HTML y devuelve una copia. El parametro *deep* es un valor booleano que indica si el se clonan el sub-árbol del elemento clonado.

El uso de estos métodos solo los crea y guarda en memoria. No están presentes en el documento HTML aún.

#### Métodos para insertar elementos en el DOM

- **nodoPadre.appendChild(*nodoHijo*)**: inserta nodoHijo como el último hijo de nodoPadre.

```js
document.body.appendChild(imagen);
```

- **nodoObjetivo.insertAdjacentElement/HTML/Text(posición, elemento/str/texto)**: Se inserta un nodo elemento, código HTML o un nodo texto en la posición indicada. Hay 4 opciones de posición:
    - *beforebegin*: El elemento se inserta antes de la etiqueta HTML de apertura.
    - *afterbegin*: El elemento se inserta dentro de la etiqueta HTML, antes de su primer hijo.
    - *beforeend*: El elemento se inserta dentro de la etiqueta HTML, después de su último hijo. Es el equivalente a usar el método .appendChild().
    - *afterend*: El elemento se inserta después de la etiqueta HTML de cierre.

```js
document.body.insertAdjacentElement("afterbegin", imagen);
document.body.insertAdjacentElement("afterend", imagen);
document.body.insertAdjacentElement("beforebegin", imagen);
document.body.insertAdjacentElement("beforeend", imagen);
```

- **nodoPadre.insertBefore(nodoNuevo, nodoReferencia)**: inserta nodoNuevo en nodoPadre antes de nodoReferencia.

#### Métodos para eliminar contenido en el DOM

- **nodoPadre.removeChild(hijo)**: remueve el hijo de nodoPadre en el DOM y devuelve una referencia a hijo.

```js
const div = document.querySelector(".item:nth-child(2)");   // <div class="item">2</div>
document.body.removeChild(div); // Desconecta el segundo .item
```

#### Métodos para reemplazar contenido

- **nodo.textContent**: Devuelve el contenido de texto del elemento. Se puede asignar para modificar.

```js
parrafo1.textContent = "Hola desde el párrafo 1";
console.log(parrafo1.textContent);
```

- **nodo.innerHTML**: Reemplaza el contenido del elemento con formato HTML.

```js
const parrafo4 = document.getElementById('parrafo4');
parrafo4.textContent = "Modificando el contenido desde JavaScript"
parrafo4.innerHTML = '<a href="https://google.com">Enlace</a>';  // Reemplaza el texto con un enlace a google.com dentro del elemento <p>
```

- **nodo.outerHTML**: // Reemplaza el elemento original por completo con el valor del outerHTML.

```js
const parrafo4 = document.getElementById('parrafo4');
parrafo4.outerHTML = '<a href="https://google.com" id="parrafo4" >Enlace</a>'; // Sustituye el elemento <p> por <a>
```

> **NOTA:**
> Los métodos para agregar marcado HTML debe ser utilizado con cuidado ya que pueden crear riesgos de seguridad si se emplean de manera equivocada. [Video al respecto](https://www.youtube.com/watch?v=ns1LX6mEvyM)

### Modificar atributos HTML

```js
div.setAttribute('id', 'theDiv'); // if id exists, update it to 'theDiv', else create an id with value "theDiv"

imagen.src = 'https://placeimg.com/200/200/animals';
imagen.alt = 'Imagen aleatoria de animales obtenida de placeimg.com';

div.getAttribute('id');  // returns value of specified attribute, in this case
// "theDiv"

div.removeAttribute('id');  // removes specified attribute
```

### Modificar CSS en línea

```js
div.style.backgroundColor = 'blue';  // adds the indicated style rule
div.style.cssText = 'color: blue; background: white;';  // adds several style rules
div.setAttribute('style', 'color: blue; background: white;');  // adds several style rules
```

### Trabajar con clases CSS mediante en el DOM

```js
const div = document.querySelector(".element");
// Obtener clases CSS
div.className;              // "element shine dark-theme"
div.getAttribute("class");  // "Mismo resultado"

// Modificar clases CSS
div.className = "elemento brillo tema-oscuro";
div.setAttribute("class", "elemento brillo tema-oscuro");

// Utilizar classList para manipular clases 
div.classList.add('new');  // adds class "new" to your new div
div.classList.remove('new');  // removes "new" class from div
div.classList.toggle('active');  // if div doesn't have class "active" then add it, or if it does, then remove it
```

## Eventos
Los eventos son notificaciones que toman lugar cuando el usuario de una página realiza una acción determinada. Existen tres formas de configurar eventos: mediante una funcion definida directamente dentro de un atributo de evento en la etiqueta HTML, mediante la configuracion de la propiedad `on_event` en el objeto del DOM en el archivo JavaScript, o mediante la configuración de `addEventListener`.

### Evento mediante HTML 
Es la forma mas sencilla, pero menos recomendable, porque se mezcla código JS en el documento HTML. Este método está limitado a un evento `onclick` por elemento.
```js
<button onclick="alert('Hola, gracias por saludarme')">SALUDAR</button>
```

### Evento mediante elemento DOM en Javascript
Es una forma alternativa de gestionar eventos, creando HTML desde la API DOM. En lugar de agregar el atributo `onclick` al botón, lo localizamos mediante `querySelector` o `getElementById`. Luego le asignamos una función con el codigo deseado.
```js
const btn = document.querySelector("#btn");
btn.onclick = () => alert("Hola desde el JS");
```
Este método sigue teniendo el problema de que un elemento DOM  puede tener una sola propiedad `onclick`.

### Evento mediante `addEventListener`
Permite agregar una escucha del evento indicado como primer parametro, y en el caso de que ocurra, se ejecuta la funcion asociada indicada como segundo parametro.
```js
// Sintaxis de addEventListener
target.addEventListener(evento, callback([*event*]));
						
// Ejempplo
btn.addEventListener("click", () => alert("Hola, saludos con un Event Listener"));
```
El argumento opcional *event* de la función *callback*  es un objeto que hace referencia al propio evento. El objeto evento contiene propiedades y métodos para conocer el detalles específicos sobre un evento (como que tecla o botón del ratón fue pulsado) o información acerca del *target* del evento, el nodo del DOM que activó el evento.
