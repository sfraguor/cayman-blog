# Peticiones AJAX Básicas
##### Ejemplos de referencia: http://ajaxref.com/ch2/

### [Aprende javascript con MentoringJS - Pretraining Step 7](http://mentoringjs.com)

```
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
```

##### Hacer una petición requiere dos llamadas: 
  ```
  request.open('GET', 'https://davidwalsh.name/ajax-endpoint', true);
  request.send(null);
  ```

La primera define el tipo de petición y la segunda ejecuta la petición.

##### Añadir cabeceras:
```
request.setRequestHeader('request.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
```
##### Peticiones Callback

Tenemos dos formas de actuar sobre el resultado de una request:

Controlando el cambio de estado:
 ```   
  request.onreadystatechange = function() {
    if(request.readyState === 4){ // done
      if(request.status === 200){ //complete
        console.log(request.responseText)
      }
    }	
  };
``` 
Con addEventListener
```
function callbackFn(e) {
	// Manejar cada evento
}

request.addEventListener("progress", callbackFn, false);
request.addEventListener("load", callbackFn, false);
request.addEventListener("error", callbackFn, false);
request.addEventListener("abort", callbackFn, false);
```

Para acabar de aprender todo lo referente a las XMLHttpRequest es interesante estudiar el siguiente enlace donde nos explican porque no usar peticiones sincronas y el uso del objeto FormData.

https://developer.mozilla.org/es/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest

Podemos también ver un ejemplo más completo con addEventListeners
```
var req = new XMLHttpRequest();

req.addEventListener("progress", updateProgress, false);
req.addEventListener("load", transferComplete, false);
req.addEventListener("error", transferFailed, false);
req.addEventListener("abort", transferCanceled, false);

req.open();

...

// progress on transfers from the server to the client (downloads)
function updateProgress(evt) {
  if (evt.lengthComputable) {
    var percentComplete = evt.loaded / evt.total;
    ...
  } else {
    // Unable to compute progress information since the total size is unknown
  }
}

function transferComplete(evt) {
  alert("The transfer is complete.");
}

function transferFailed(evt) {
  alert("An error occurred while transferring the file.");
}

function transferCanceled(evt) {
  alert("The transfer has been canceled by the user.");
}
```


