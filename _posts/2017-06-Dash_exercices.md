# Dash Exercices 1 to 3

### [Aprende javascript con MentoringJS - Pretraining Step 3](http://mentoringjs.com)

### Block vs Inline vs Inline-block
Siempre se me olvida la diferencia entre estos 3 valores y he encontrado esta web donde te lo explican de forma que se entiente muy bien.

https://alligator.io/css/display-inline-vs-inline-block/

text-align solo puede alinear BLOQUES no puede alinear elementos INLINE

### Background-size Cover vs 100%

Al principio me costó un povo porque eran diferentes estas asignaciones, pero encontré un ejemplo en codepen que enseguida me ayudóa a ver la diferencia.

Como vemos en el ejemplo cuando asignamos a la propiedad background-size = 100%, la imagen se adapta a la anchura del contenedor padre manteniendo la altura en proporción, de manera que tal y como se ve en el ejemplo puede quedar parte del contenedor vacío. Si por el contrario asignamos el valos cover a la propiedad, la prioridad es cubrir todo el area del contenedor padre sin variar la proporción, y la única manera de conseguir esto es aumentando la anchura y la altura proporcionalmente hasta cubrir todo perdiendo parte de la imagen, ya que el contenedor padre actua como una especie de máscara.

Ejemplo en codepen: https://codepen.io/netmagik/pen/vEvjaG

Es mejor no asignar a las imagenes una anchura y altura especificas con CSS.

Los navegadores leen el CSS desde la parte de arriba a la de abajo

### Las media queries
En estos ejercicios nos introducen el uso de las media queries, pero muy por encima, si hacemos tal y como nos van guiando no ofrece ningun problema, pero hay muchas más opciones en el uso de las media queries que me interesaba conocer y he buscado más información. Podemos hacer media queries en base a muchos más parámetros de los que nos muestran estos ejercicicios y viene bien tenerlos en cuenta.

Estas dos webs me han servido para conocer mejor el uso de las media queries.

https://medium.freecodecamp.com/the-100-correct-way-to-do-css-breakpoints-88d6a5ba1862
https://developer.tizen.org/development/guides/web-application/w3chtml5supplementary-features/user-interface/media-queries


### Transition & Vendor prefixes

Otro de los puntos que esta serie de ejercicios ha pasado muy por encima es el tema de las transiciones y de los vendor prexies y por eso he buscado información para complementar estos aspectos mientras realizaba los ejercicios.

https://www.w3schools.com/css/css3_transitions.asp
https://www.thoughtco.com/css-vendor-prefixes-3466867

Si queremos olvidarnos de estar pendientes de los vendor prefixes existen erramientas que nos ayudan a añadirlos sin que nos tengamos que preocupar.

https://marketplace.visualstudio.com/items?itemName=mrmlnc.vscode-autoprefixer

