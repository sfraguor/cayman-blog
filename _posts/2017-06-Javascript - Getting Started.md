
# Javascript - Getting Started
### [Aprende javascript con MentoringJS - Pretraining Step 2](http://mentoringjs.com)

Antes de empezar a trabajar con proyectos en Javascript es muy importante tener las bases claras. Para aprender estos conceptos el primer cápitulo del libro Speaking Javascript es un muy buen inicio.

http://speakingjs.com/es5/ch01.html

A continuación he realizado una pequeña síntesis de conceptos, dudas y aclaraciones que me han surgido en el momento de la lectura y que servirán como recordatorio y tabla de consulta rápida por si tenemos dudas más adelante. Sobre todo he querido incluir los conceptos más importantes y los que pueden ser un poco confusos al principio.

### Conceptos que debemos tener claros en Javascript (Esta lista puede actualizarse si surgen nuevos conceptos importantes)

- Statements: Instrucciones a ser ejecutadas por el navegador.
- Expressions: Una expresión es cualquier unidad válida de código que resuelve un valor.
- Variables: Son contenedores para guardar valores.
- Funciones: Una función son un conjunto de sentencias que realizan una tarea o calculan un valor.
- Objetos: Grupo de propiedades y funciones que pueden ser accedidos a través de una clave.
- Métodos: Un método es una función asociada a un objeto, o, simplemente, un método es una propiedad de un objeto que es una función
- Scope: Alcance o ámbito sobre el que tienen efecto por ejemplo unas variables
- Encapsular: La encapsulación se refiere a impedir el acceso a determinados métodos y propiedades de los objetos estableciendo así que métodos y propiedades de estos pueden ser utilizados desde el resto del código

#### Variables

Las variables en Javascript se definen con la palabra clave **var** pudiéndo dar un valor a esta variable en el momento de crearla:

var test1;
var test1=0;

Las variables son en javascript son "hoisted" sin embargo, pero las asignaciones no lo son y esto es importante tenerlo en cuenta.
[Hoisting en Javascript](http://www.etnassoft.com/2010/12/26/hoisting-en-javascript/)

#### Valores primitivas, Objetos y Propiedades

Es fundamental tener claros estos conceptos. 
Los valores primitivos son los valores más simples que tiene javascript y son los boleanos, los numeros, los strings y el valor null, undefined y symbol(ES6).
Los objetos, son entidades independientes que pueden tener propiedades, y estas propiedades son las que definen al objeto. Es decir, si tenemos un objeto coche, este objeto podrá tener definidas propiedades como: tamaño, color, numero de ruedas, velocidda que alcanza ...
Las propiedades por tanto serán las características asociadas a los objetos y **una vez definidas no pueden ser cambiadas, añadidas o borradas**.

var prueba = 1;
var prueba2 = { 
  nombre: "Prueba de ciencias",
  dificultad: 2,
  numeroPaginas: 3
};

En este caso tenemos la variable prueba que tiene asignado un valor primitivo y el objeto prueba2, tiene las propiedades : nombre, dificultad y numeroPaginas.

### Undefined and null ([Más información](http://www.enrique7mc.com/2016/01/diferencia-entre-null-y-undefined-en-javascript/))

Estos valores llamados "nonvalues" son importantes en Javascript y enseguida que empecemos a desarrollar con el lenguaje nos daremos cuenta de que vamos a verlos y utilizarlos muy amenudo. Estos valores pueden dar lugar a confusion y esta confusión puede dar lugar errores lógicos o bugs difíciles de encontrar y por eso es muy importante entender la diferencia.

**Undefined**

Cuando una variable se declara pero todava no tiene valor asignado = undefined, y esto se aplica tambien a los parámetros de una función:

var miVariable; //miVariable tiene un varlor undefined.

function foo(bar) {}
foo(); // El parámetro bar tiene un valor undefined.

Undefined es un tipo de dato y por lo tanto, lo podemos asignar a una variable, sin embargo es preferible que nunca asignemos directamente el valor undifined, ya que cunado nos encontremos con una variable de este tipo no estaremos seguros si fue javascript o nosotros quien le asignamos ese valor, y eso nos puede generar problemas más adelante.

**Null**

Null representa la ausencia de valor intencional, es decir que somos nosotros intencionadamente los que asignamos este valor a una variable cuando no sabemos que valor va a contener.

var test = null;

#### Funciones

Otra de los conceptos que hemos de tener claros son las funciones, las funciones son fundamentales y es primordial tener muy claro su funcionamiento.

La forma más común cuando aprendemos de declarar una función y pasarle parámetros es la siguiente:

**function add(param1, param2) {
    return param1 + param2;
}**

Pero en muchas ocasiones veremos como se asigna la función y luego esta función se utiliza a través de la variable en la que se ha almacenado. Este método es muy común en Javascript y lo encontraremos en múltiples ocasiones.

**var add = function (param1, param2) {
    return param1 + param2;
};** 

Sin embargo, he decidido investigar un poco más para saber cual de estos dos métodos de declaración es más correcto y he encontrado el siguiente e interesante artículo: [Diferencias a la hora de definir funciones](http://qbit.com.mx/blog/2013/08/23/formas-de-crear-funciones-en-javascript/)

#### Closures

Este concepto no lo conocía apenas y sin embargo me he dado cuenta de lo importante que es tenerlo claro. Por eso he buscado información y he encontrado este fantástico artículo, que recomiendo leer repetidas veces hasta poder asimilar todos los conceptos. A mi todavía me quedan unas cuantas lecturas.

[Closures](https://jherax.wordpress.com/2015/02/13/javascript-closures/)

#### Objetos y constructores

**var jane = {
    name: 'Jane',

    describe: function () {
        return 'Person named '+this.name;
    }
};**

- Objeto con las propiedades name y describe, podemos obtener y asignar valores a estas propiedades, asi como crear nuevas propiedades.
- A las propiedades que contienen funciones como en este caso describe se les llama métodos.

**Constructores

Los constructores me resultan complicados de entender, he intentado buscar algun articulo que me ayude a entenderlo y el que me ha ayudado más ha sido el siguiente. Todavía tengo que volver a leerlo unas cuantas veces para poder tenerlo completamente claro.

http://www.programania.net/diseno-de-software/entendiendo-los-prototipos-en-javascript/











