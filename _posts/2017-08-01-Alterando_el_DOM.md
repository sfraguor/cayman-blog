# Alterando el DOM

### [Aprende javascript con MentoringJS - Pretraining Step 7](http://mentoringjs.com)

La creación del Document Object Model (DOM), es una de las innovaciones que más ha influido en el desarrollo de las páginas web dinámicas y de las aplicaciones web más complejas.

DOM permite acceder y manipular las páginas XHTML como si fueran documentos XML. DOM se diseñó originalmente para manipular de forma sencilla los documentos XML.

Las acciones más comunes que debemos conocer y saber hacer cuando trabajamos con el DOM, son las siguientes:

#### 1. Seleccionar elementos HTML

Para realizar la selección de elementos html, utilizaremos básicamente 2 métodos:

querySelector y querySelectorAll

Con el primero, seleccionaremos un elemento html, si este método se encuentra con dos elementos con la misma característica, este método solo va a devolver el primer elemento.

##### 1.1 document.querySelector(selector)

Para elegir el tipo de elemento a seleccionar, debemos colocar el tipo de elemento junto con el nombre dentro de los paréntesis y utilizaremos los mismos selectores que en html,
de forma que si queremos seleccionar un elemento a través de su clase utilizaremos: '.nombreclase', si lo queremos seleccionar mediante su id utilizaremos '.nombreid'.

Ejemplos:

```
document.querySelector('#nombreID'); //Selección a través de su ID
document.querySelector('.nombreCLASE'); //Selección a través de su CLASE
document.querySelector(p); //Selección a través del TAG
```

###### 1.1.1 Selección dentro de selectores

```
document.querySelector('.container .inner-item');
```

De esta manera estamos seleccionando el elemento con la clase .inner-item que esta dentro del elemento con clase .container.

##### 1.2 document.querySelectorAll(selectors) - Selección de múltiples elementos

```
document.querySelectorAll('.elemento1, .elemento2');
```

Algo a tener muy en cuenta es que querySelectorAll devuelve un NodeList, y que es un nodeList y como trabajar con el?

Tenemos que tener claro que un nodeList no es un array, puedes recorrer un nodeList y hacer referencias como en un array pero, nu puedes
usar métodos como valueOf(), push(), pop(), o join().

Podemos ver más ejemplos en la siguiente url: https://www.w3schools.com/js/js_htmldom_nodelist.asp

#### 2. Añadir y eliminar listeners(elementos de escucha)

addEventListener / removeEventListener

Para poder añadir el listener, primero debemos seleccionar el elemento: 

```
let thing = document.querySelector('.thing');
thing.addEventListener(event, callback);
```

El evento addEventListener acepta dos parametros, el evento a escuchar y la función que se efectuará cada vez que se detecte el evento.

```
thing.addEventListener('click', callback);
function callback(e){
  console.log('thing is clicked');
}
```

¿Que son los callback?

Una función callback consiste en llamar a una función y enviarle por parámetro otra función(callback) de forma que la función inicial
se encarga de llamar a esta.

Ejemplo1:

```
function funcionPrincipal(callback){
  alert('Hago algo y llamo al callback avisando que he terminado');
  callback();
}

funcionPrincipal(function(){
  alert('terminó de hacer algo');
});
```

Ejemplo2:

```
function funcionPrincipal(callback1, callback2, callback3){
  //código de la función principal 
  callback1();
  callback2();
  callback3();
}

function callback1(){
  alert('primer callback');
};
function callback2(){
  alert('segundo callback');
};
function callback3(){
  alert('tercer callback');
};

funcionPrincipal(callback1,callback2,callback3);
```

Un texto muy interesante para aprender sobre la asincrona en javascript y el uso de callbacks es el siguiente: 

https://carlosazaustre.es/manejando-la-asincronia-en-javascript/

```thing.removeEventListener('click',callback);```

Eliminaremos un EventListener después de que una tarea se complete:

```
thing.addEventListener('click', callback);
function callback(){
  console.log('');
  thing.removeEventListener('click',callback)
}
```

Porque debemos eliminar un listener? Porque de esta manera estamos liberando recursos para otras tareas.

#### 3. Añadir o eliminar clases

Añade: ```element.classList.add('classname');```
Elimina: ```element.classList.remove('classname');```
Comprueba si existe: ```element.classList.contains('classname');```

#### 4. Añadir, cambiar o eliminar atributos

Obtener atributo: ```button.getAttribute('aria-expanded');```
Introducir atributo: ```button.setAttribute('aria-expanded', 'true');``` (el segundo parámetro es el valor que daremos al atributo)
Eliminar atributo: ```button.removeAttribute('aria-expanded');```

#### 5. Añadir o eliminar elementos HTML

AÑADIR ELEMENTO Y AÑADIR CONTENIDO:

``` let li = document.createElement('li'); (Creamos el elemento)
li.innerHTML = "Hello again, world";   (Creamos el contenido del elemento)
ul.append(li);                         (Insertamos el elemento y su contenido en el DOM: nodoPadre.prepend o nodoPadre.append)
```

ELIMINANDO ELEMENTOS Y CONTENIDO

Primero deberemos seleccionar el elemento exacto a eliminar y una vez seleccionado, 

```
let parent = document.querySelector('.parent');
let elToRemove = document.querySelector('.element-to-remove');
parent.removeChild(elToRemove);
```




