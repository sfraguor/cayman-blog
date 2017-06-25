# Gestión de multicuentas con GIT

### [Aprende javascript con MentoringJS - Pretraining Step 4](http://mentoringjs.com)


Lo normal a la hora de trabajar con GIT es tener una sola cuenta, pero en ocasiones si queremos separar nuestros proyectos del trabajo con los personales o con una cuenta de algun curso.
Esto podría parecer simple, solamente debemos crear otra cuenta en GIT y hacer login en la cuenta que nos interese sin embargo cuando queremos hacer pull o push a una cuenta o a otra desde 
nuestra máquina local nos encontramos que no es nada sencillo y si lo intentamos, nos aparecerá un mensaje que nos dice que no tenemos permisos.

La forma que he conseguido para que funcione sigue el siguiente tutorial de la página [codetuts](https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574) hasta el punto 3, 
ya que no he conseguido que funcione el punto 4.

Una vez tenemos realizado hasta el punto 3, tan solo tenemos que tener en cuenta una cosa, al clonar el repositorio tenemos que hacerlo con el siguiente comando, y de esta manera,
siempre que trabajemos en ese repositorio podremos hacer pulls y push sin problemas.

A la hora de clonar el repositorio, cambiamos a la opción SSH y nos aparecera algo parecido a esto: **git@github.com:sfraguor/testing.git**
simplemente tenemos que añadir el nombre que hemos puesto al nuevo SSH que en esta caso es CURSO por lo tanto lo añadiremos de la siguiente manera.

**git clone git@github-CURSO:sfraguor/testing.git**







 
