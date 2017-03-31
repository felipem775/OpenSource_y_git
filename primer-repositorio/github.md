# Alta y configuración

Simplemente iremos a la página de registro [https://github.com/join](https://github.com/join) y rellenaremos el formulario. Nos enviarán un correo de confirmación a la cuenta que les hayamos proporcionado.

Una vez que tengamos nuestra cuenta nos pedirá rellenar información sobre nosotros \(opcional\) y podemos activar la autentificación en dos pasos \(opcional\) que consiste en que nos enviarán un sms cuando nos identifiquemos en un equipo nuevo, por lo que además de la clave, necesitaremos tener el teléfono.

## Clave SSH

Aunque no está relacionado con el desarrollo de software, para poder trabajar con nuestro cliente de git en github debemos tener una pareja de claves SSH y subir la parte pública a nuestra cuenta de GitHub.  
Para subirlo correctamente está explicado en la propia web [https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

# Clone vs Fork

En GitHub los repositorios públicos nos los podemos descargar sin ningún problema, podemos utilizar `git clone` y dispondremos tanto de los ficheros actuales como de todo el histórico que ha habido en el repositorio.

Si queremos simplemente utilizar un proyecto alojado en github, con git clone será suficiente. Sin embargo si queremos desarrollar sobre él, la opción que debemos utilizar es la del _fork_.

Un _fork_ consiste en que el proyecto elegido se copia a nuestra cuenta de usuario, respetanto todo su historial y autorías, y se crea una referencia entre el proyecto original y el nuestro. En nuestra versión ya podremos hacer todos los cambios que queramos. Más adelante veremos cómo podemos solicitar al autor del proyecto original que incluya nuestros cambios.

Es importante tener en cuenta que una vez que hacemos un fork del proyecto, se nos copia en el estado de ese momento, si el proyecto original se modifica, esto no se verá reflejado en nuestro proyecto a no ser que lo hagamos manualmente.

## Clone vs Fork. En la práctica

El proyecto de la calculadora está publicado en la siguiente página: [https://github.com/felipem775/pyCalc](https://github.com/felipem775/pyCalc)

![](/assets/felipem775-pyCalc.png)

### Clone 
Si deseamos **solo descargar el código**, utilizamos el botón de **Clone or download**
** que nos dará la información para realizar un `git clone` o bien un zip solo con los ficheros del proyecto pero sin repositorio.

Para clonar el repositorio usaremos:

    git clone git@github.com:felipem775/pyCalc.git

Puede que nos solicite una contraseña, ésta es la contraseña de nuestra clave SSH, no la de GitHub.

```
Cloning into 'pyCalc'...
remote: Counting objects: 12, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 12 (delta 1), reused 12 (delta 1), pack-reused 0
Receiving objects: 100% (12/12), done.
Resolving deltas: 100% (1/1), done.
Checking connectivity... done.
```

Ahora podremos trabajar en el repositorio de manera local pero no subir cambios.

### Fork
Si deseamos tener una copia en github que podemos actualizar, deberemos utilizar el botón de **fork**.
Este realizará una copia del repositorio y cuando vayamos al listado de nuestros repositorios lo tendremos ahí.

![](/assets/gogoigo-pyCalc.png)

Debajo del título aparece la información que es fork del proyecto pyCalc del usuario felipem775, y si vamos al proyecto original vemos que ahora aparece que tiene un fork. Esto puede ser muy útil cuando un proyecto deja de tener mantenimiento pero alguien ha decidido hacer un fork y seguir mejorándolo.

Para **descargarnos nuestro fork** utilizaremos la opción de **clone** con la dirección del ahora nuestro proyecto:

    git clone git@github.com:gogoigo/pyCalc.git

Ahora, igual que si hubieramos clonado el repositorio ajeno, podremos trabajar con él en local y, además, podremos subir los cambios a GitHub.

# Enviando nuestros cambios a nuestro proyecto
Vamos a realizar un cambio en nuestro proyecto y realizar el commit, por ejemplo, añadir la codificación para que pueda ejecutarse en python2

    $ git add suma2numeros.py 
    $ git commit -m "añadida codificación utf8, ahora ya no falla con python 2" 

Tras el commit está actualizado en el repositorio local y ahora vamos a enviarlo al repositorio remoto, para ello vamos a usar

    git push

```
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 375 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local objects.
To git@github.com:gogoigo/pyCalc.git
   2b50e4a..f87d1a6  master -> master
```


# Deshacer el último commit de github
Si accidentalmente hemos enviado un commit a nuestro repositorio remoto, podemos deshacerlo con el comando:

    git push -f origin HEAD^:master
