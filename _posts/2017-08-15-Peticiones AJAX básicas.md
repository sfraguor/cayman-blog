# Peticiones AJAX Básicas
##### Ejemplos de referencia: http://ajaxref.com/ch2/

´´´
var request;
if (window.XMLHttpRequest) { // Mozilla, Safari, ...
  request = new XMLHttpRequest();
} else if (window.ActiveXObject) { // IE
  try {
    request = new ActiveXObject('Msxml2.XMLHTTP');
  } 
  catch (e) {
    try {
      request = new ActiveXObject('Microsoft.XMLHTTP');
    } 
    catch (e) {}
  }
}
´´´

##### Hacer una petición requiere dos llamadas: 
  
  request.open('GET', 'https://davidwalsh.name/ajax-endpoint', true);
  request.send(null);

La primera define el tipo de petición y la segunda ejecuta la petición.

##### Añadir cabeceras:

request.setRequestHeader('request.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');

##### Peticiones Callback

Tenemos dos formas de actuar sobre el resultado de una request:

Controlando el cambio de estado:
    
  request.onreadystatechange = function() {
    if(request.readyState === 4){ // done
      if(request.status === 200){ //complete
        console.log(request.responseText)
      }
    }	
  };
 
Con addEventListener

function callbackFn(e) {
	// Manejar cada evento
}

request.addEventListener("progress", callbackFn, false);
request.addEventListener("load", callbackFn, false);
request.addEventListener("error", callbackFn, false);
request.addEventListener("abort", callbackFn, false);
