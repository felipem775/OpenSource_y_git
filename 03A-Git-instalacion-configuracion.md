[Git](http://git-scm.com/) es un **software de control de versiones distribuido**. Aunque existen muchas alternativas, Git es en la actualidad el más popular por su facilidad de uso, estabilidad, versatilidad y gestión eficiente de grandes proyectos.  
Otro sistema de versiones que utilizamos en el IH es [SVN](http://subversion.apache.org/) \(Subversion\) pero éste es más antiguo y con más limitaciones.

# Instalación y configuración de git

## Descarga e instalación
En la web oficial nos explican cómo descargarlo e instalarlo en diferentes sistemas operativos https://git-scm.com/downloads.  
Se trata de un programa CLI, la interface es la línea de comandos pero podemos instalar también alguna GUI (programa visual) disponibles en https://git-scm.com/downloads/guis/.  
Aunque de entrada pueda parecer más complicada, la línea de comandos es bastante sencilla para trabajar con git. En estos tutoriales trabajaremos siempre desde ella.

## Configuración
De los siguientes elementos a configurar solo es obligatorio el de _Identidad_.

### Identidad
Antes de permitirnos hacer cualquier commit, nos obliga a definir una identidad. Debemos establecer nuestro nombre y email.

    $ git config --global user.name "John Doe"
    $ git config --global user.email johndoe@example.com

Hemos utilizado el parámetro `--global` para que sean los datos por defecto. Posteriormente en cualquier repositorio podremos modificar estos datos solo para él.

### Editor
Podemos establecer un editor de textos para añadir los comentarios a nuestros commits

Linux:

    $ git config --global core.editor nano

Windows:

    $ git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -nosession"

### Otros parámetros y comprobación
Podemos ver la configuración actual con:

    $ git config --list

Normalmente estos datos se almacenan en `/etc/gitconfig` y `~/.gitconfig`
