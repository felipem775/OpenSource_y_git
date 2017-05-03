# hooks
Podemos configurar acciones que se ejecuten cuando hagamos acciones en el repositorio. Por ejemplo, cada vez que hago un commit de este repositorio, se lanza un script que genera la versión html del mismo.

Estos scripts se localizan dentro de la carpeta _.git/hooks_ del proyecto, por defecto nos aparecen unos ficheros de ejemplo, pero son solo una muestra de los eventos disponibles, hay muchos más. En el caso comentado antes crearemos un fichero _post-commit_, y en él añadimos la siguiente instrucción:

    exec gitbook build ~/GitBook/Library/OpenSource_y_git/

Otros casos en los que puede ser útil añadir hooks.

* Antes de realizar commit ejecutar los tests
* Notificaciones cuando se hace un push
* Reiniciar un servicio que utiliza directamente código del repositorio.
* Realizar un despliegue al recibir cambios

Podemos encontrar más ejemplos e información en el siguiente enlace:

https://www.digitalocean.com/community/tutorials/how-to-use-git-hooks-to-automate-development-and-deployment-tasks
