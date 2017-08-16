## TwitchTV WEBAPP 

Para realizar este ejercicio se ha partido de un ejercicio en JQuery en el siguiente repositorio GIT.
https://github.com/rocio-m-sebastian/twitchtv

Antes de empezar con el ejercicio se ha leido y revisado la documentación de la API de la plataforma SWITCHTV.
https://dev.twitch.tv/docs

Como vemos, lo primero que hay que darse cuenta es que la plataforma dispone de 2 versiones de API que debemos seleccionar, cada una con sus particularidades. Después de dar un vistazo vemos que nuestro ejercicio utiliza la v3.

Al principio el ejercicio en jQuery no cargaba los canales, una vez revisado, fue necesario cambiar un poco la url de la API a la que vamos a hacer la petición ya que requiere de un client ID que se obtiene registrandose en la plataforma y creando una APP de prueba en la seccion de desarrollo. Una vez hecho esto se nos facilitara el client ID que ahora mostraremos donde se ha introducido.

Lo primero que hacemos es crear un array con los nombres de los canales

```
var channels = ["freecodecamp", "ESL_SC2", "OgamingSC2", "cretetion", "llilka", "habathcx", "noobs2ninjas", "lizbethbobomb", "bifuteki"];

```

Seguidamente definimos la funcion principal getChannelInfo cuya funcion es crear las listas de los canales

```
 function getChannelInfo() {};
 
```

Dentro de esta funcion ejecutaremos otra funcion para cada uno de los elementos del array channels. Esto lo realizaremos con un forEach y le pasaremos el parametro channel que equivaldra a cada elemento del array en cada paso del forEach.

```
function getChannelInfo() {

  channels.forEach(function(channel){
    
  });

};

```

El siguiente paso es generar la URL a la que vamos a hacer las peticiones. Esta URL en nuestro caso, varia ligeramente en función de lo que queramos que nos devuelva la API, si queremos que nos devuelva streams o si queremos que nos devuelva los channels.

Para ello utilizaremos la siguiente funcion:

```
function makeURL(type, name) {
      return 'https://api.twitch.tv/kraken/' + type + '/' + name + '?client_id=io29h4le6jv32mnmrc3lhsezgzjwbx';
};
```

```
function getChannelInfo() {
  channels.forEach(function(channel){
    function makeURL(type, name) {
      return 'https://api.twitch.tv/kraken/' + type + '/' + name + '?client_id=io29h4le6jv32mnmrc3lhsezgzjwbx';
    };
  });
};

```

Empezamos con las peticiones, primero la peticion GET:

    var xhr2 = new XMLHttpRequest();
    xhr2.open('GET', makeURL("streams", channel));
    xhr2.setRequestHeader('Content-Type', 'application/json');
    xhr2.onload = 
     function() {
     }
     
Cargamos una cabecera del tipo JSON y una vez recibida la respuesta de la petición, ejecutamos una serie de acciones a traves de la siguiente funcion:

Guardamos en una variable la respuesta que hemos obtenido en formato JSON como string y debemos parsearlo para que sea un objeto Javascript:

    var parsedJSON_2 = JSON.parse(xhr2.responseText);
     
Creamos dos variables mas, la variable status y la variable game.

    var status, game;

Comprobamos si la respuesta de la petición contiene el canal o no lo contiene



