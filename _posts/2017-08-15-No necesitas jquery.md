
No necesitas jQuery

** GETing - XMLHttpRequest (Petición AJAX)

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

En este ejemplo, creamos un nuevo objeto XMLHttpRequest(), llamamos al metodo GET, pasando la direccion de donde obtener los datos, realizamos las operaciones que queramos y posteriormente realizamos la peticion HTTP al servidor con el metodo send.

Si queremos mas informacion sobre este objeto, podemos consultar la siguiente direccion donde nos lo explica muy detalladamente:

http://librosweb.es/libro/ajax/capitulo_7/metodos_y_propiedades_del_objeto_xmlhttprequest.html

** POSTing - XMLHttpRequest (Petición AJAX)

var newName = 'John Smith';
var xhr = new XMLHttpRequest();

xhr. open('POST', 'myservice/username?id=some-unique-id');
xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
xhr.onload = function() {
	if (xhr.status === 200 && xhr.responseText !== newName){
		alert();
	}
	else if (xhr.status !==200){
		alert ();
	}
};

