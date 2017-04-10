Podemos configurar ciertos aspectos de nuestro repositorio si creamos en el directorio raíz del proyecto los siguientes ficheros: `.gitignore`, `.gitattributes`.

# .gitignore
Podemos crear una lista de ficheros o patrones para los ficheros que no queremos gestionar con git. Algunos ficheros que no nos interesan tener son: logs, ficheros de configuración con contraseñas, ficheros temporales, ficheros que se han compilado pero no nos interesan.

```    
    # Byte-compiled / optimized / DLL files
    *.py[cod]
    *$py.class
    # Installer logs
    pip-log.txt
    pip-delete-this-directory.txt
```

En GitHub disponemos de un repositorio con los _.gitignore_ más habituales dependiendo del lenguaje que estemos usando. [Repositorio de ficheros .gitignore](https://github.com/github/gitignore).

# .gitattributes
Por defecto git trata a todos los ficheros como texto pero en ocasiones tendremos ficheros que serán binarios como imágenes o aunque en parte sean planos trabajamos con ellos de diferente forma, como .docx; estos ficheros no se pueden comparar entre ellos como si fueran texto, ni es óptimo almacenarlo con el mismo sistema.

```
    *.py 		text
    *.py3 		text
    *.db		binary
    *.p 		binary
    *.pkl 		binary
    *.pyc 		binary
```    
En GitHub disponemos de un repositorio con los _.gitattributes_ más habituales dependiendo del lenguaje que estemos usando. [Repositorio de ficheros .gitattributes](https://github.com/alexkaratarakis/gitattributes)
