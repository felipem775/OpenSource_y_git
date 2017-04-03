# Qué es
Un _Branch_ es una ramificación en el repositorio que utilizaremos para realizar cambios en nuestro código.
Cuando queremos añadir los cambios de una rama a otra los mezclamos con _merge_.
A continuación veremos por qué y cómo hacerlo.

# Por qué
En nuestro primer repositorio hemos ido avanzando en el programa y añadiendo los cambios a nuestro repositorio. Estos cambios se han hecho sin trabajar con ramas, o más bien trabajando en la rama por defecto: **master**, éste es el tronco de nuestro repositorio y en él deberíamos tener la última versión funcional de nuestro proyecto. 
Si queremos realizar modificaciones del código, es posible que queramos hacer commits durante el avance y que estos provoquen que hasta que no se terminen los cambios la aplicación no funcione correctamente, por eso **desarrollamos en ramas**.
Por ejemplo, en la aplicación de la calculadora vamos a hacer que además de sumar se pueda restar, multiplicar y dividor dos cifras. Simplemente cambiar y hacer commit para que acepte 3 parámetros en lugar de los 2 actuales, hará que hasta que no terminemos el nuevo desarrollo nadie pueda utilizar la aplicación.
Si nos llevamos el desarrollo a otra rama, una persona que descargue _master_ podrá utilizarlo con los últimos cambios completos que tenga. Mientras, nosotros trabajando en el branch podremos hacer todos los commits que queramos.

# Crear una rama
Comandos que usaremos: `git branch`, `git checkout`.

    $ git branch mas-operaciones
    $ git branch 
        mas-operaciones
      * master

Con `git branch <nombre>` creamos un branch con el estado actual de la rama en la que estamos. Es decir, acabamos de crear una rama llamada _mas-operaciones_ con el contenido en este momento que tiene _master_. 
Con `*` nos marca qué branch es el actual, seguimos en _master_, al crear el branch no cambiamos al nuevo así que si hacemos nuevos commits serán sobre _master_. Si hacemos cambios en la rama _master_ éstos no se ven reflejados en _mas-operaciones_.

    $ git checkout mas-operaciones 
    Switched to branch 'mas-operaciones'

Con `git checkout` cambiamos y activamos el branch seleccionado. En este momento no notaremos más cambios, pero más adelante con los commits veremos que sí.

# Renombrar ficheros
Comandos que usaremos: `git mv`, `git add`, `git commit`.
El nombre actual, _suma2numeros.py_ no es el más apropiado, así que vamos a renombrarlo. 

Utilizamos un comando _git_ para renombrar, si lo hacemos sin utilizar _git_, el repositorio a veces no detecta que es el mismo fichero y perderá las referencias antiguas sobre él.

    git mv suma2numeros.py calculadora.py
    
    git add calculadora.py
    git commit -m "Renombrado a un nombre más adecuado"
    
    [mas-operaciones 12cee3a] Renombrado a un nombre más adecuado
    1 file changed, 0 insertions(+), 0 deletions(-)
    rename suma2numeros.py => calculadora.py (100%)

# Push en branches
Cuando anteriormente hicimos _push_, los cambios de nuestro repositorio _master_ se enviaron al branch _master_ remoto. Es el comportamiento por defecto cuando se ejecuta _git clone_.
Si desde el nuevo branch intentamos hacer un push, nos pedirá configurar a qué rama del repositorio remoto queremos hacerlo, no es necesario que coincida el nombre.


    $ git push
    fatal: The current branch mas-operaciones has no upstream branch.
    To push the current branch and set the remote as upstream, use

        git push --set-upstream origin mas-operaciones



    $ git push --set-upstream origin mas-operaciones
    Total 0 (delta 0), reused 0 (delta 0)
    To git@github.com:gogoigo/pyCalc.git
     * [new branch]      mas-operaciones -> mas-operaciones
    Branch mas-operaciones set up to track remote branch mas-operaciones from origin.
    
Una vez que hemos definido el branch remoto, el resto de push desde el branch actual irán a ese branch

# Checkout
Antes vimos como con `git checkout` nos movíamos entre diferentes branches. Al hacer esto los ficheros se actualizan al estado de ese branch y para ello si es necesario se borran y se crean otros.         

Si estamos en mas-operaciones tenemos los siguientes ficheros:

    $ ls
    calculadora.py	README.md
    
Si cambiamos a master cambiará:

    $ git checkout master
    Switched to branch 'master'
    Your branch is up-to-date with 'origin/master'.
    
    $ ls
    README.md  suma2numeros.py

Git guarda los datos de cada archivo que hay en todos los branches en su directorio `.git`, por lo que no perderemos ningún archivo registrado al movernos de uno a otro branch.
        
                                                
# Merge
Para llevar los commits de un branch a otro, el método es el de importar. 
En nuestro proyecto actual nos interesa llevar los datos del branch _mas-operaciones_ a _master_, así que iremos al branch _master_ y desde ahí importaremos las novedades con `merge`

    $ git checkout master
    $ git merge mas-operaciones 
    Updating 3d8dd82..2790751
    Fast-forward
     suma2numeros.py => calculadora.py | 0
     1 file changed, 0 insertions(+), 0 deletions(-)
     rename suma2numeros.py => calculadora.py (100%)

En este caso el cambio es sencillo, renombra nuestro fichero

---
Por otro lado, mientras hacemos un desarrollo de funcionalidad podemos querer hacer otros cambios que no tienen que ver con el desarrollo actual, como corregir un texto o un bug, y además que sea urgente. Haremos otra rama.
Mientras estaños añadiendo la nueva funcionalidad nos piden que el script sea autoejecutable. Es un cambio de una sola línea si es urgente no podemos esperar a terminar el desarrollo actual.


