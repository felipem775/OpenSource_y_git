Otro fichero de configuración para nuestro repositorio es `.gitattributes`,

Por defecto git trata a todos los ficheros como texto pero en ocasiones tendremos ficheros que serán binarios como imágenes o aunque en parte sean planos trabajamos con ellos de diferente forma, como .docx; estos ficheros no se pueden comparar entre ellos como si fueran texto, ni es óptimo almacenarlo con el mismo sistema.

Para especificar si un fichero o los que responden a un patrón son de cierto tipo, creamos en la raíz del proyecto el fichero `.gitattributes` y en él vamos especificando el tipo de fichero y cómo tratarlo.
