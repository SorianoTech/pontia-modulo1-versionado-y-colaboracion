Para proteger el la rama principal he macarado la opcion "Require a pull request before merging", en target branches he seleccionado "main" y he activado la opción "Enforce Active".

Esta configuración impide que se puedan hacer commits directamente en la rama principal, obligando a que todos los cambios se realicen a través de una solicitud de fusión (pull request).

Dejo marcadas las opciones por defecto "Block force pushes" y "Restrict deletions" y marco "Restrict updates" para impedir actualizaciones de la rama principal.


Justificacion .gitignore

En el archivo .gitignore he agregado los archivos de "*.log" y el directorio "__pycache__/" de cache de Python.