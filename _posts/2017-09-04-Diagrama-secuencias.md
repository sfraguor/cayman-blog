
# Diagrama de secuencias
### [Aprende javascript con MentoringJS - Pretraining Step 8](http://mentoringjs.com)
#### Que es un diagrama de secuencia?

El Diagrama de Secuencia es un tipo de diagrama usado para modelar interacción entre objetos en un sistema según UML. UML es el Lenguaje Unificado de Modelado, es un lenguaje gráfico para visualizar, especificar, construir y documentar un sistema.

El Tiempo fluye hacia abajo en el diagrama y muestra el flujo de control de un participante a otro al transcurrir de un tiempo.

#### Para que se usa?

Los diagramas de secuencia nos ayudan a planear, visualizar y entender la estructura de nuestra aplicación en terminos de clases y jerarquías.

#### De que se componen estos diagramas?

El diagrama consta de dos dimensiones, una horizontal de la disposición de los objetos y otra dimensión vertical del paso del tiempo.

· Los objetos estan representados como rectngulos con un texto subrayado y se colocan en la parte superior del diagrama, de izquierda a derecha, la línea punteada que se desprende del rectángulo es conocida como línea de vida del objeto, y junto con esta línea aparece un pequeño rectángulo llamado activación, que represente la ejecución que realiza el objeto. La longitud del rectángulo se interpreta como la duración de la activación.

· Los mensajes se representan con una línea continua que termina con una punta de flecha. Esta pasa de una línea de vida de un objeto a otra. Un objeto puede enviarse un mensaje a si mismo.
  
##### Hay distintos tipos de mensajes:

- Mensaje Simple: representa la transferencia de un control a otro.
- Mensaje Sincrono: cuando se envía este mensaje es porque se necesita una respuesta antes de continuar. Los mensajes síncronos se utilizan para representar llamadas de función ordinarias dentro de un programa, asi como otros tipos de mensaje que se comportan de la misma manera.
- Mensaje Asíncrono: es un mensaje que no requiere una respuesta antes de que el remitente continue. Un mensaje asincrono muestra solu una llamada del remitente. Se utiliza para representar la comunicacion entre subprocesos diferentes o la creación de un nuevo suproceso.

##### TIEMPO

El tiempo esta representado por una progresion vertical. El tiempo se inicia en la parte superior y avanza hasta la parte inferior, un mensaje que este en la parte superior ocurrir antes que un mensaje que esta en la parte inferior.

Como ejemplo pasaremos a diagrama de secuencias el ejercicio realizado en el step anterior sobre la plataforma SWITCH. Para ello he utilizado la siguiente web https://www.websequencediagrams.com que a través de una serie de intrucciones va generando el diagrama :

He intentado simplificarlo bastante empezando por una división inicial de 3 participantes (usuario, sistema y api) de forma que los relacionaremos entre ellos cuando haya una llamada a la API o alguna petición al sistema.

Como vemos, lo que haremos en primer lugar es realizar una petición por parte del usuario al sistema(que equivaldra al servidor) para que empiece a ejecutarse, en este caso la web.

Una vez realizada la petición de a sistema, este se prepara obteniendo los parametros necesarios para realizar las llamadas a la API y una vez ya dispone de estos parametros, lanza las peticiones a la API y esta devuelve los valores solicitados para finalmente visualizar la interfaz de los streams con los canales correspondientes.

```
participant usuario
participant sistema 
participant api_switch

title Switch App sequence

usuario->sistema: iniciar_sistema()
sistema->sistema: parametros para la petición de los streams
sistema->sistema: obtener cabecera de los streams (json)
sistema->sistema: parametros para la petición de los canales
sistema->sistema: obtener cabecera de los canales (json)
sistema->api_switch: petición de los streams
sistema->api_switch: petición de los canales
api_switch->sistema: respuesta de la petición streams
api_switch->sistema: respuesta de la petición canales
sistema->usuario: devuelve la interfaz con los streams y sus canales

```

Mas referencias sobre diagramas de secuencias:

http://www.monografias.com/trabajos67/diagramas-uml/diagramas-uml2.shtml
http://www.w3ii.com/es/uml/uml_interaction_diagram.html









