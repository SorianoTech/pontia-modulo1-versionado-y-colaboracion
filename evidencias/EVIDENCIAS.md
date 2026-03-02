Estudiante: Sergio Soriano San Jose
Repositorio: [https://github.com/SorianoTech/pontia-modulo1-versionado-y-colaboracion](https://github.com/SorianoTech/pontia-modulo1-versionado-y-colaboracion)

## 1. Configuración y Protección de la Rama Main

Para proteger el la rama principal he macarado la opcion **"Require a pull request before merging"**, en target branches he seleccionado "main" y he activado la opción "Enforce Active".

Esta configuración impide que se puedan hacer commits directamente en la rama principal, obligando a que todos los cambios se realicen a través de una solicitud de fusión (pull request).

Dejo marcadas las opciones por defecto "Block force pushes" y "Restrict deletions" y marco "Restrict updates" para impedir actualizaciones de la rama principal. Posteriormente, me doy cuenta de que no se puede hacer un pull request a la rama principal por lo que vuelvo a desmarcar la opcion "Restrict updates".

**¿Por qué proteger la rama principal?** En un proyecto real, esto evita que errores accidentales lleguen a producción, asegura que el código sea revisadoy permite que las pruebas automáticas (CI) validen los cambios antes de la integración final.

## 2 Justificacion .gitignore

Se ha configurado un archivo .gitignore en la rama feature/gitignore con los siguientes criterios:

En el archivo .gitignore he agregado los archivos de "*.log" y el directorio "__pycache__/" de cache de Python.

- *.log: Ignora todos los archivos de registro para evitar ensuciar el historial con datos temporales.

- __pycache__/: Ignora los directorios de caché de Python que son específicos de cada máquina.

**Nota:** La verificación de que estos archivos no son rastreados por Git se encuentra en el archivo evidencias/gitignore-status.txt

## 3. Resolución de conflictos

Durante la integración de las funcionalidades de suma y resta, se produjo un conflicto en el archivo operations.py.

- Origen del conflicto: Ambas ramas (feature/suma y feature/resta) intentaron modificar las mismas líneas de código partiendo de una base común.

- **Resolución**: Se realizó un merge de main hacia feature/resta en local. Se editaron manualmente las marcas de conflicto para combinar las funciones info(), suma() y resta().

- **Evidencia visual:** El historial completo y la ramificación se detallan en evidencias/git-log.txt

4. **Automatización con GitHub Actions** 

Se ha implementado un flujo de trabajo (workflow) en .github/workflows/demo.yml que permite la ejecución manual.

**Funcionamiento:** Al activarse mediante workflow_dispatch, el sistema solicita el nombre del usuario como entrada y lo imprime en la consola de la máquina virtual de GitHub.

- **Resultado:** La salida confirmada de la ejecución se encuentra en evidencias/action-output.txt

## 5. Flujo de Trabajo Seguido

El desarrollo se ha basado en el modelo GitHub Flow:

1. Creación de ramas descriptivas para cada tarea.
2. Commits frecuentes con mensajes claros.
3. Apertura de Pull Requests para revisión e integración.
4. Sincronización constante del repositorio local con el remoto.