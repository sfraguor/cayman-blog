
# No necesitas jQuery
### [Aprende javascript con MentoringJS - Pretraining Step 7](http://mentoringjs.com)

## GETing - XMLHttpRequest (Petición AJAX)

```

   var xhr = new XMLHttpRequest();
   xhr.open('GET', 'myservice/username?id=some-unique-id');
   xhr.onload = function() {
	if (xhr.status ===200) {
	alert('User\ 's name is ' + xhr.responseText);
	}
	else {
		alert(''Request failed. Returned status of' + xhr.status)
	}
   };
   xhr.send();
   
```

En este ejemplo, creamos un nuevo objeto XMLHttpRequest(), llamamos al metodo GET, pasando la direccion de donde obtener los datos, realizamos las operaciones que queramos y posteriormente realizamos la peticion HTTP al servidor con el metodo send.

Si queremos mas informacion sobre este objeto, podemos consultar la siguiente direccion donde nos lo explica muy detalladamente:

http://librosweb.es/libro/ajax/capitulo_7/metodos_y_propiedades_del_objeto_xmlhttprequest.html

Para acabar de entender mejor es interesante el siguiente artículo y sobre todo el ejemplo

https://www.kirupa.com/html5/making_http_requests_js.htm

## POSTing - XMLHttpRequest (Petición AJAX)

```
var newName = 'John Smith';
var xhr = new XMLHttpRequest();

xhr. open('POST', 'myservice/username?id=some-unique-id');
xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
xhr.onload = function() {
	if (xhr.status === 200 && xhr.responseText !== newName){
		alert('Something went wrong.  Name is now ' + xhr.responseText);
	}
	else if (xhr.status !==200){
		alert('Request failed.  Returned status of ' + xhr.status);
	}
};

xhr.send(encodeURI('name=' + newName));

```

## URL Encoding (Convertir un objeto a un string codificado)

```
function param(object) {
	var encodeString = '';
		for (var prop in object){
			if(object.hasOwnProperty(prop)){
				if (encodedString.length > 0){
					encodedString += '&';	
				}
				encodedString += encodeURI(prop + '=' + object[prop]);
			}
		return encodedString;
}
```

## Enviando y recibiendo JSON 

Actualizando la información (PUT).
Actualizamos la información del usuario 1234.

```
var xhr = new XMLHttpRequest();
xhr.open('PUT', 'myservice/user/1234');
xhr.setRequestHeader('Content-Type', 'application/json');
xhr.onload = function() {
	if (xhr.status === 200){
		var userInfo = JSON.parse(xhr.reponseText);
	}
};

xhr.send(JSON.stringify({
	name: 'John Smith',
	age:34
}));
```
Resulta muy interesante seguir los ejercicios que encontraremos en esta web para practicar y ver como funcionan todas
las llamadas AJAX que estamos aprendiendo.

http://ajaxref.com/ch3/

Podemos pensar, que diferencia entonces PUT de POST?

La w3.org nos lo explica. https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html#sec9.6

La diferencia fundamental entre las peticiones POST y PUT está reflejada en el diferente significado de la Request-URI.
El URI en una petición POST identifica el recurso que manejará la entidad incluida. Ese recurso podría ser un proceso de aceptación de datos, una puerta de enlace a algún otro protocolo o una entidad separada que acepte anotaciones.
En contraste el URI en una petición PUT, identifica la entidad incluida con la solicitud, el user agent sabe a que URI está destinado y el servidor NO DEBE tratar de aplicar la solicitud a algún otro recurso.
Si el servidor desea que se aplique a una URI diferente, DEBE enviar una respuesta 301(Moved Permanently); El user agent PUEDE entonces tomar su propia decisión con respecto a si redirigir o no la solicitud.




