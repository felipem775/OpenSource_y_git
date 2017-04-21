GitHub, a través de su [plataforma Pages](https://pages.github.com/), nos da la posibilidad de publicar webs para nuestros proyectos de manera gratuita y sin publicidad, incluso añadiendo un dominio propio. Las páginas deben ser estáticas aunque también admite para el gestor de contenidos [jekyllrb](https://jekyllrb.com/).

La página principal tendrá como url **_usuario_.github.io**, y a él le podremos añadir subdirectorios con la página de los repositorios que tengamos alojados.

Así, para el usuario gogoigo, la url es _gogoigo.github.io_, para ello creamos un repositorio con ese mismo nombre y en su branch _master_ colocamos a nivel raíz la página _index.html_ que queramos mostrar.

Si queremos publicar una web de nuestro proyecto _pyCalc_, la forma de publicar cambia ligeramente.
* No dispondrá de una URL propia sino que será un subdirectorio. Para nuestro proyecto _pyCalc_ la dirección que le corresponde es: _ https://gogoigo.github.io/pyCalc/_ .
* La ubicación de los ficheros que se quieran publicar deberán estar en alguna de las siguientes ubicaciones:
  * Raíz del branch _master_, es decir, el código entero es publicado como web.
  * Raíz del branch _gh-pages_, de manera que este branch tiene un contenido independiente del código de proyecto.
  * En la carpeta _/doc_ del branch _master_. A modo de documentación podemos poner la página del proyecto.
* Deberemos activar el la configuración de cada proyecto, si deseamos que se muestre o no la página web del proyecto, y ahí indicaremos cuál de las 3 ubicaciones anteriores es la que contiene la web.
