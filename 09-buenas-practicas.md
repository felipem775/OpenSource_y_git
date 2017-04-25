

# Fichero README.md
El primer fichero que se busca en un repositorio es el **README.md**. Se trata de un fichero en formato _markdown_ donde, sin ser un manual, se explica brevemente de qué trata el proyecto, cómo usarlo y qué licencia utiliza.  

# Nunca desarrollar en _master_
La rama principal del repositorio es llamada _master_, en ella siempre debemos tener la última versión del código que funcione completa, por lo que no podemos tener desarrollos a medias.

# Comentarios útiles en los commits
Igual que los comentarios en el código, es importante que detallemos en lo posible los mensajes del commit. Ya no solo porque lo vaya a leer otra persona, sino porque es posible que nosotros mismos lo hagamos dentro de muchos meses y no recordemos el por qué de cierto cambio.

# Realizar el commit deben ser de todos los ficheros implicados
Cuando hacemos un commit debemos detallar los cambios que aportamos, por ello es importante que añadamos todos los ficheros implicados en lugar de hacer varios commits.
Ej. Añadir una dependencia y su referencia. Añadir fichero completion y su referencia en .bashrc

# En cada rama solo desarrollamos lo relacionado con la feature
Mientras estamos desarrollando una característica nos pueden pedir que corrijamos o modifiquemos algún fallo que se ha detectado en la versión de master. Aunque sea un cambio pequeño, debemos ir a master, crear una rama nueva a partir ahí, solucionarlo en la nueva rama, volver a master, hacer merge, regresar a la rama donde estábamos trabajando y también hacer merge para tomar el nuevo cambio en nuestro código.

# Merge con --no-ff
Cuando traemos los commits de otro branch, por defecto se añaden al histórico del branch actual sin ningún rastro de que haya sido desarrollado aparte. Si añadimos la opción `--no-ff` sí que se agruparán todos los commits que traemos, y no nos será costoso localizar en la historia commits anteriores y posteriores.

# Recuerda etiquetar versiones del software.
Cuando nuestro proyecto alcance algún hito, además de realizar el commit correspondiente, podemos hacer un tag para que en el futuro podamos acceder fácilmente a ese estado del proyecto.
Ej. Versión 0.1

# Intentar solo tener código fuente
Debemos evitar añadir binarios que no sean imprescindibles, en especial:
  * Bibliotecas externas. Deberá documentarse la dependencia pero no incluirlo en el repositorio.
  * Binarios generados en nuestro proyecto. Los ejecutables y bibliotecas deberían compilarse cada vez. Las única excepción podría ser cuando generamos una versión estable y etiquetada.
