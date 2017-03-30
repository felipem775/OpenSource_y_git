Para facilitar el manual vamos a crear un proyecto de ejemplo: Una calculadora en python.

Como cualquier otro proyecto, por sencillo que sea no lo vamos a desarrollar completo y bien a la primera. Vamos a proponernos unos hitos.

* Crear un script que sume dos cifras.
* Modificar el script para añadir diferentes operaciones.

# Preparando el proyecto
Comandos que usaremos:
* git init: Iniciamos un repositorio.
* git add: Marcamos un fichero para el próximo commit.
* git commit: Realizamos un commit de los ficheros marcados.

Creamos la carpeta pyCalc en el directorio /home/user/workspace/ y abrimos el terminal dentro de ella.

    $  git init
    Initialized empty Git repository in /home/mazaf/workspace/pyCalc/.git/

Ahora creamos un fichero llamado README.md donde añadiremos una descripción del proyecto que vamos a comenzar. Este será el primer archivo que incorporemos al repositorio git.

    git add README.md 
    git commit

Al realizar el commit se nos abre un editor donde introducir un comentario sobre con qué estamos actualizando el repositorio. Podemos escribir tantas líneas como queramos, las  que empiezan con `#` no se almacenarán.

# v0.1 Crear un script que sume dos cifras

Vamos a hacer un script que al ser llamado le pasemos dos números y nos devolverá la suma.

    import sys
    print(int(sys.argv[1]) + int(sys.argv[2]))

    $ python3 suma2numeros.py 2 3
    5

Este script, aunque muy simple y mejorable, es capaz de realizar el primer hito. Vamos a guardar los cambios en el repositorio.

    git add suma2numeros.py 
    git commit 

Aunque cumple el objetivo del hito, vamos a añadirle alguna característica como que compruebe que se le están pasando dos números.
Mientras añadimos estas características nos fijamos que solo podemos sumar números enteros. ¡es un bug!
Aunque es muy fácil de resolver, primero debemos terminar la otra funcionalidad para hacer commit y luego ya arreglaremos el bug y haremos commit de esto.

    git add suma2numeros.py 
    git commit -m "Añadida validación de que se trata de dos parámetros y que éstos son números"

Ahora ya podemos corregir el bug y añadirlo al repositorio

    git add suma2numeros.py 
    git commit -m "corregido bug, ahora suma números como float y no solo enteros"




