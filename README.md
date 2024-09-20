`git --version`  
Muestra la versión instalada de git

`git config --global user.name "Nombre"`  
`git config --global user.email "Correo@correo.com"`  
Configura el nombre y correo global para todos los repositorios creados.


`git config user.name "OtroNombre"`  
`git config user.email "OtroCorreo@correo.com"`  
Configura el nombre y correo solo para el repositorio actual. 
Útil cuando se tiene que diferenciar en una misma computadora proyectos personales de proyectos del trabajo.


`git config --list`  
Muestra la configuración actual.


`git config user.name`  
`git config user.email`  
Muestra las configuraciones de nombre y correo.


`ssh-keygen -t ed25519 -C "Correo@correo.com"`  
Genera una clave SSH y la guarda en ~/.ssh/id_ed25519.

`eval "$(ssh-agent -s)"`  
Inicia un agente SSH.

`ssh-add ~/.ssh/id_ed25519`  
Añade la clave SSH generada al agente.

`cat ~/.ssh/id_ed25519.pub`  
Muestra la clave pública SSH. Copiar para los settings de GitHub.

`ssh -T git@github.com`  
Autentica la clave SSH con GitHub. Si es exitoso sale este mensaje:
Hi [NombreUsuario]! You've successfully authenticated, but GitHub does not provide shell access.


`git init`  
Inicia un nuevo repositorio en el directorio actual.

`git status`  
Muestra el estado del repositorio.

`git status --short`
`git status -s`  
Muestra un resumen del estado del repositorio.

`git add [Archivo/Carpeta]`  
Añade archivos o carpetas al área de staging.  
Ejemplos  
`git add index.html`  
`git add *.js`  
`git add .`

`git add -A`  
Añade todos los cambios del proyecto al área de staging. Estando en la carpeta raíz es equivalente a git add .  
pero si estamos parados en un subdirectorio sigue añadiendo los cambios de todo el repositorio.

`git add -u`  
Añade solo modificaciones y eliminaciones al área de staging. No las creaciones de nuevos archivos/carpetas.

`git reset`  
Revierte los cambios desde el área de staging.

`git commit -m "[Mensaje]"`  
Crea un commit con los cambios en staging.

`git log`  
Lista todos los commits.

`git log --oneline`  
Lista todos los commits de manera resumida.

`git log -n [N]`  
Lista los últimos N commits.

`git clone [RepoURL]`  
Clona un repositorio.


### Ramas

`git branch`  
Muestra todas las ramas existentes y la rama actual.

`git switch [NombreRama]`  
Cambia a la rama con el nombre especificado

`git switch -c [NombreRama]`  
Cambia a la rama con el nombre especificado, si no existe la crea

`git branch -d [NombreRama]`  
Elimina una rama

`git merge [NombreRama]`  
Fusiona la rama en la que estás con la rama especificada

`git checkout --theirs [NombreArchivo]`  
Si ocurre un conflicto, deja las modificaciones de la rama externa

`git checkout --ours [NombreArchivo]`  
Si ocurre un conflicto, deja las modificaciones de la rama en la que estamos



`git diff`  
Fusiona la rama en la que estás con la rama especificada

`git show`  
Muestra los datos del último commit

`git show [CodCommit]`  
Muestra los datos del commit especificado



### Stash

`git stash`  
Guarda las modificaciones del entorno de trabajo en una pila llamada Stash

`git stash save "[Nombre]"`  
Permite guardar con un nombre identificador

`git stash --include-untracked`  
Guarda los archivos modificados y los nuevos archivos sin trackear

`git stash list`  
Muestra la pila de Stash si es que tiene elementos

`git stash pop`  
Retorna el espacio de trabajo a el último stash guardado

`git stash pop stash@{[NumeroID]}`  
Retorna el espacio de trabajo a el stash con el identificador asociado


### Checkout
`git checkout [archivo]`  
Si el archivo fue modificado, lo retorna a como estaba en el último commit

`git checkout .`  
Retorna todo a como estaba en el último commit

`git revert [CodCommit]`  
Genera un nuevo commit revirtiendo los cambios que se hicieron en un commit anterior


### Reset
`git reset --soft HEAD~1`  
Deshace el commit manteniendo los cambios en el area de staging

`git reset HEAD~1`  
Deshace el commit manteniendo los cambios en el area de trabajo

`git reset --hard HEAD~1`  
Deshace el commit y deshace los cambios

### Modificar último commit
`git commit --amend`
Se puede modificar el nombre del último commit  

Si nos olvidamos un cambio para agregar al commit lo agregamos al área de staging
`git add .`  
`git commit --amend`  
Y automáticamente lo agrega al último commit

