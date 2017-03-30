# Alta y configuración
Simplemente iremos a la página de registro https://github.com/join y rellenaremos el formulario. Nos enviarán un correo de confirmación a la cuenta que les hayamos proporcionado.

Una vez que tengamos nuestra cuenta nos pedirá rellenar información sobre nosotros (opcional) y podemos activar la autentificación en dos pasos (opcional) que consiste en que nos enviarán un sms cuando nos identifiquemos en un equipo nuevo, por lo que además de la clave, necesitaremos tener el teléfono.

## Clave SSH
Aunque no está relacionado con el desarrollo de software, para poder trabajar con nuestro cliente de git en github debemos tener una pareja de claves SSH y subir la parte pública a nuestra cuenta de GitHub.
Para subirlo correctamente está explicado en la propia web https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/


# Clone vs Fork
En GitHub los repositorios públicos nos los podemos descargar sin ningún problema, podemos utilizar `git clone` y dispondremos tanto de los ficheros actuales como de todo el histórico que ha habido en el repositorio.

Si queremos simplemente utilizar un proyecto alojado en github, con git clone será suficiente. Sin embargo si queremos desarrollar sobre él, la opción que debemos utilizar es la del _fork_. 

Un _fork_ consiste en que el proyecto elegido se copia a nuestra cuenta de usuario, respetanto todo su historial y autorías, y se crea una referencia entre el proyecto original y el nuestro. En nuestra versión ya podremos hacer todos los cambios que queramos. Más adelante veremos cómo podemos solicitar al autor del proyecto original que incluya nuestros cambios.

Es importante tener en cuenta que una vez que hacemos un fork del proyecto, se nos copia en el estado de ese momento, si el proyecto original se modifica, esto no se verá reflejado en nuestro proyecto a no ser que lo hagamos manualmente.

## Clone vs Fork. En la práctica
He subido el proyecto de la calculadora a GitHub y si queremos verlo simplemente visitamos la página https://github.com/felipem775/pyCalc

![](/assets/felipem775-pyCalc.png)

Si deseamos solo descargar el código, utilizamos el botón de _Clone or download_ que nos dará la información para realizar un `git clone` o bien un zip solo con los ficheros del proyecto pero sin repositorio.
