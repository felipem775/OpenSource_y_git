# branch
Un branch es una línea de desarrollo, debemos pensar en el repositorio como un árbol, y cada _branch_ lo forma un conjunto de _commits_.
Cuando queremos realizar nuevos cambios en el código, lo habitual es crear una nueva rama donde poder manipular el código con total libertad.

# commit
Como nombre: Se trata de cada uno de los puntos que componen la historia del repositorio. Se podría considerar a cada commit una revisión o versión del repositorio.
Como verbo: Se trata del momento en el que añadimos los cambios de un repositorio a la historia.

# origin
Es el nombre que se da por defecto al repositorio remoto.

# merge
Como verbo: Traer a nuestro branch el estado de otro branch.

# pull
Recibir los commits de una rama de un repositorio remoto en la rama de nuestro repositorio local.

# push
Enviar los commits de la rama de nuestro repositorio local a una rama de un repositorio remoto.

## git init
Iniciamos un repositorio. Para ello generará una carpeta `.git` en la carpeta donde lo ejecutemos y dentro contendrá los ficheros que él necesite.

## git add
Marcamos un fichero para el próximo commit.

## git remote
Git es un servicio distribuido, por lo que podemos añadir la ubicación de otros repositorios con los que trabajar en nuestro proyecto.

## git diff
Nos permite comparar entre diferentes commits. Podemos ver qué ficheros se han modificado y qué líneas se han quitado o puesto.
