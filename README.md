>git -- version  
Muestra la versión instalada de git

>git config --global user.name "Nombre"  
>git config --global user.email "Correo@correo.com"  
Esta va a ser la configuración global para todos los repositorios creados


>git config user.name "OtroNombre"  
>git config user.email "OtroCorreo@correo.com"  
Para cambiar la configuración de un repositorio específico. Útil cuando se tiene que diferenciar en una misma computadora proyectos personales de proyectos del trabajo.


>git config --list
Muestra la configuración


>git config user.name
>git config user.email
Muestran las configuraciones especificadas


>ssh-keygen -t ed25519 -C "Correo@correo.com"
Genera una llave ssh, se pide frase y se guarda por defecto en ~/.ssh/id_ed25519
>eval "$(ssh-agent -s)"
Genera un agente SSH
>ssh-add ~/.ssh/id_ed25519
Añade la clave generada al agente ssh
>cat ~/.ssh/id_ed25519.pub 
La salida de este comando debe copiarse en los settings de github
>ssh -T git@github.com
Hi [NombreUsuario]! You've successfully authenticated, but GitHub does not provide shell access.


>git init
Inicia el repositorio

>git status
Muestra el estatus del repositorio

>git status -s
Muestra una versión minimizada del estatus del repositorio

>git add [NombreDelArchivo/Carpeta]
Añade el/los archivo/s al area de staging
Ejemplos
>git add index.html
>git add *.js
>git add .

>git add -A 
Añade todos los cambias al repositorio. Estando en la carpeta raíz es equivalente a git add .  
pero si estamos parados en un subdirectorio sigue añadiendo los cambios en todo el repositorio.

>git add -u 
Añade todas las modificaciones u eliminaciones, pero no las creaciones de nuevos archivos.

>git reset
Devuelve los cambios en archivos a la zona de trabajo

>git commit -m "[Mensaje]"
Añade los archivos en el área de staging al área del repositorio. 

>git log
Lista todos los commits

>git log --oneline
Lista todos los commits de manera minimizada

>git log -n [N]
Lista los últimos N commits

>git clone [RepoURL]
Clona un repositorio


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
Si ocurre un conflicto, deja las modificaciones de la rama interna



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

