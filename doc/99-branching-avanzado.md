En el artículo [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/) nos explican una buena práctica del uso de branches.

A continuación veremos un resumen del artículo aplicado a lo aprendido en esta serie de tutoriales.

![esquema](/assets/git-model-branching.png)

## master
En el esquema podemos ver el branch máster a la derecha, en él solamente aparecen los _tag_ o versiones.  
En este branch nunca desarrollaremos, solo lo utilizaremos para lanzar las versiones estables de nuestro proyecto, cada vez que introduzcamos cambios en este _branch_ lo etiquetaremos.

## develop
En esta rama vamos a ir añadiendo todas las features que desarrollemos, estas versiones son llamadas _inestables_ y en algunos proyectos los usuarios pueden acceder a ellas en lugar de esperar a que se desarrollen todas las features para lanzar una versión _mayor_/_estable_, teniendo en cuenta que no es un producto final.

## feature
Cuando queramos desarrollar una nueva feature, haremos un branch nuevo desde _develop_ y una vez terminado enviaremos los cambios de nuevo a _develop_. Si estamos desarrollando más de una feature a la vez, cada una va a un branch diferente y siempre parten desde _develop_.

## release branch
Cuando ya dispongamos de las features en _develop_ para pasar crear una versión estable, generaremos un branch para realizar las pruebas y corregir los fallos que detectemos antes de publicar la nueva versión. Nunca meteremos nuevas _features_ en este branch. Una vez que hayamos dado el visto bueno, desde _master_ tomaremos los cambios de esta rama, y también desde _develop_.

## hotfix
En ocasiones encontramos en la versión estable algún bug que necesitamos corregir sin esperar a la siguiente versión estable. Generamos un _branch_ a partir de _master_ y una vez corregido, enviamos los cambios a _master_ donde etiquetaremos con la nueva versión menor y también lo enviaremos a _develop_ para que no se pierdan los cambios hechos en la siguiente versión.
