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