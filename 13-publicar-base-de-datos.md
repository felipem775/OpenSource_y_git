# Publicar bases de datos

A la hora de publicar nuestras bases de datos, lo haremos como scripts SQL.

Todos los motores de bases de datos disponen de herramientas para realizar un \*dump\* tanto de la estructura como de los datos.

## Pasos:

1. Realizaremos una copia de la base de datos donde solo la dejaremos poblada con los datos que se quieran difundir.
2. Realizaremos un _dump_ de la BD solo con la estructura \(tablas, relaciones de columnas, etc.\) y lo guardaremos en un fichero llamado `schema.sql`

3. Realizaremos un segundo _dump_ de la BD solo con los datos y lo guardaremos en un fichero llamado `data.sql`

4. Estos dos ficheros los guardaremos en la carpeta `/db/`



```
.
+-- db/
|   -- schema.sql
|   -- data.sql
```




