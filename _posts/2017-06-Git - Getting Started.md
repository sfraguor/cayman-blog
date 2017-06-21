# Git - Getting Started
### [Aprende javascript con MentoringJS - Pretraining Step 2](http://mentoringjs.com)

Tener los conceptos básicos de la herramienta de versionado GIT, es fundamental para trabajar en el mundo del desarrollo web y es por eso que es importante tener claros los conceptos base de esta herramienta.

Para ello, una guía fundamental para aprender estos conceptos de forma clara y práctica cuando nos estamos iniciando en el uso de GIT es la siguiente guía que nos ofrece la siguiente guía.

https://www.codeschool.com/courses/try-git

#### Resumen de comandos y conceptos GIT aprendidos

Lo primero que tenemos que tener en cuenta antes de poder utilizar la herramienta GIT en nuestros archivos locales es que debemos tener la herramienta instalada. Para ello lo mejor es que introduzcamos en la linea de comandos de windows, mac o linux el comando: **git --version** para que nos muestre la versión que tenemos de git.
Si no reconoce el comando significará que no tenemos git instalado y que por tanto lo primero que tenemos que hacer es instalarlo.

En la página oficial nos explican como hacerlo en función de nuestro sistema operativo.

https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

Una vez instalado, ya podemos empezar a utilizar los comandos. Para poder empezar a trabajar con git tenemos que tener el cliente inicializado en el directorio raiz en el que queramos trabajar, de manera que una vez lo hayamos hecho cualquier variación quedar registrada por git.

El primer comando que deberemos utilitasr por tanto la primera vez que iniciemos un proyecto que queramos controlar con git es: 

**git init**

El siguiente comando que utilizaremos es para ir viendo en que estado estan los archivos de este directorio con respecto a GIT. Para ello usaremos el comando

**git status**

Una vez realicemos cualquier tipo de cambio en este directorio, GIT lo registrará y situará los cambios en una especie de cola y nosotros debemos decir a GIT si queremos poner esos archivos a seguimiento para posteriormente hacer un commit.

Usaremos por tanto la orden **git add** y el nombre del fichero o ficheros que queramos situar a seguimiento o si queremos situar todos los archivos a seguimiento, utilizaremos la orden **git add -A**

A la hora de añadir todos los archivos a seguimiento podemos encontrarnos con 3 ordenes muy parecidas y que pueden llevarnos a confusión por lo que aconsejo leer este enlace para tenerlo claro: https://atrystwithprogramming.wordpress.com/tag/git-add-vs-git-add/

Una vez añadidos los archivos para seguimiento el siguiente paso natural sería realizar un commit utilizando para ello el comando:

**git commit -m "primer commit"** (donde primer commit puede ser un comentario cualquiera, sencillo y que permita identificar que queremos commitar)

Para obtener un log de los commits que vamos haciendo usaremos el comando: 

**git log**

Una vez realizado el commit, el último paso si trabajamos en remoto con github sería subir el cambio. Esta acción la realizariamos con el comando **git push origin master**. De manera que subiriamos los cambios a la rama master de nuestro repositorio remoto.

Cuando trabajamos en remoto, antes de realizar la acción **git push** debemos asegurarnos de que tenemos todos los archivos locales actualizados con los remotos. Para hacer esta sincronización haremos uso del comando **git pull origin master** y ahora si podremos realizar un push, evitando problemas.

Teniendo claros estos comandos podremos empezar a trabajar con GIT para ir cogiendo confianza, para más adelante empezar a trabajar con ramas que es la parte más interesante y potente de la herramienta.











