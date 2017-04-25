Para facilitar el manual vamos a crear un proyecto de ejemplo: Una calculadora en python.

Como cualquier otro proyecto por sencillo que sea no lo vamos a desarrollar completo y bien a la primera, por lo que será útil ir registrando los cambios en el repositorio.

# Preparando el proyecto

Comandos que usaremos: `git init`, `git add`, `git commit`.

Creamos la carpeta pyCalc en el directorio /home/user/workspace/ y abrimos el terminal dentro de ella, vamos a iniciar un nuevo repositorio, para ello utilizaremos el comando `git init`

```
$  git init
Initialized empty Git repository in /home/mazaf/workspace/pyCalc/.git/
```

Ahora creamos un fichero llamado README.md donde añadiremos una descripción del proyecto que vamos a comenzar. Este será el primer archivo que incorporemos al repositorio git.

```
git add README.md
git commit
```

Al realizar el commit se nos abre un editor donde introducir un comentario sobre con qué estamos actualizando el repositorio. Podemos escribir tantas líneas como queramos, las  que empiezan con `#` no se almacenarán.

# Crear un script que sume dos cifras

Comandos que usaremos: `git add`, `git commit`.

Vamos a hacer un script que al ser llamado le pasemos dos números y nos devolverá la suma.

```
import sys
print(int(sys.argv[1]) + int(sys.argv[2]))

$ python3 suma2numeros.py 2 3
5
```

Este script, aunque muy simple y mejorable, es capaz de realizar el primer hito. Vamos a guardar los cambios en el repositorio.

```
git add suma2numeros.py
git commit
```

Aunque cumple el objetivo vamos a añadirle alguna característica como que compruebe que se le están pasando dos números.  
Mientras añadimos estas características nos fijamos que solo podemos sumar números enteros. ¡es un bug!  
Aunque es muy fácil de resolver, primero debemos terminar la otra funcionalidad para hacer commit y luego ya arreglaremos el bug y haremos commit de esto.

```
git add suma2numeros.py
git commit -m "Añadida validación de que se trata de dos parámetros y que éstos son números"
```

Ahora ya podemos corregir el bug y añadirlo al repositorio

```
git add suma2numeros.py
git commit -m "corregido bug, ahora suma números como float y no solo enteros"
```

# Ver histórico y cambios realizados

Comandos que usaremos: `git log`, `git diff`.

Si queremos ver el histórico del repositorio simplemente usaremos el comando `git log`

     $ git log  


```   
commit 2b50e4ace5d8badf9d0246f8b2570d3f2b31b4fe  
Author: Felipe Maza <felipe.maza@unican.es>  
Date:   Thu Mar 30 10:35:19 2017 +0200

    corregido bug, ahora suma números como float y no solo enteros

commit 3f83af0de2447dffe267832a36e53e95ee068846  
Author: Felipe Maza <felipe.maza@unican.es>  
Date:   Thu Mar 30 10:34:02 2017 +0200

    Añadida validación de que se trata de dos parámetros y que éstos son números

commit 386cdcc492f0e30e0956f879eff82c63c6cebad1  
Author: Felipe Maza <felipe.maza@unican.es>  
Date:   Thu Mar 30 10:16:46 2017 +0200

    Script muy básico que suma dos números

commit 38859dba49cacb9816296cee4f58afd510330259  
Author: Felipe Maza <felipe.maza@unican.es>
Date:   Thu Mar 30 10:02:14 2017 +0200

     Añadimos el primer fichero al repositorio. Contiene una breve descripción.

```

De cada _commit_ nos da la siguiente información:
* Un identificador alfanumérico, nos servirá cuando queramos referirnos a un commit determinado.
* Autor del commit.
* Fecha en la que se ha realizado el commit.
* Comentario que escribió el autor del commit.


Si queremos ver qué cambios hay respecto a un commit, utilizaremos `git diff`

     $ git diff 3f83af0de2447dffe267832a36e53e95ee068846
```     
diff --git a/suma2numeros.py b/suma2numeros.py
index 36aebbe..59dd95c 100644
--- a/suma2numeros.py
+++ b/suma2numeros.py
@@ -10,4 +10,4 @@ elif  re.match("^[+-]?\d(>?\.\d+)?$", sys.argv[2]) is None:
     print("El segundo parámetro no es un número")

 else:
-    print(int(sys.argv[1]) + int(sys.argv[2]))
+    print(float(sys.argv[1]) + float(sys.argv[2]))


```
Aquí podemos ver qué ficheros han sido modificados, en este caso solo suma2numeros.py. Se nos indica en qué parte del fichero ha habido cambios, poniendo la línea anterior para que lo localices antes y, precedido de los signos `-` y `+` vemos qué líneas se han quitado y puesto.
En este caso vemos cómo ha desaparecido la línea donde se convertían los parámetros a números _int_ y a cambio se ha puesto una línea donde los parámetros se convierten a números _float_.

# Estado del repositorio
Comandos que usaremos: `git status`.

Podemos utilizar `git status` para ver en qué estado se encuentran nuestros ficheros respecto al repositorio.

Tras hacer un commit de todos nuestros ficheros, estaremos sincronizados con el repositorio:

    $ git status

    On branch master
    nothing to commit, working directory clean

# Fin de esta parte
Bien, con este pequeño tutorial hemos visto los aspectos básicos de lo que hace un repositorio a nivel local para un solo uso. Con esto ya sabemos más o menos la mitad de lo que utilizaremos en el día a día.

Antes de avanzar más, vamos a pasar a ver un poco github.
