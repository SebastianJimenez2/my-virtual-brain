# APUNTES DE CURSO DE GIT
Git & GitHub sirven especialmente para una materia (u otras) [[modelamiento de software]] que se ve en quinto semestre.

**Desarrollo de un proyecto**
1. Pensar el nombre de una empresa
2. Buscar un ícono

**Diferencia entre archivo de programa y usuario (carpetas)**
*- Archivos de programa:*  Instalación de sistema (pide contraseña)
*- Usuario:* No hace falta que pida contraseña 
	
**Insertar un enlace o una imagen**
Enlace --> [texto](url)
Imagen --> ![texto](https://img.shields.io/gem/u/a?color=a&label=a&logo=a&logoColor=a)
Imagen con enlace --> [![texto](https://img.shields.io/gem/u/a?color=a&label=a&logo=a&logoColor=a)](url)
	
**Qué es Git?**
Informa cambios dentro de un código

**¿Qué es GitHub?**
Es un software con un algoritmo bastante potente, servicio que tenemos en la nube

*DevOps*
1. Primero planificamos
2. Implementamos
3. Pruebas
4. Entrega
5. Despliegue
6. Mantenimiento
	
**Commit**
Es aquel que almacena la información cambiada dentro de un código. Adjunta: correo, nombre, fecha todo esto con una ID.

**Repositorios**
	- Local --> En mi computadora
	- Remoto --> En la nube

**Tipos de commit**
- *Rebase*
Cómo unir una rama principal con una rama experimental
	- Rama experimental hacia rama main

- *Merge*
Permite hacer cambios mientras experimentas
	- Pasar todo de la rama experiemental en un cambio que engloba todo

**Cosas sobre GIT** 
- LFS (Large File Support) --> Se maneja mediante índices, que no se lamacenan irectamente en el repositorio.
- Open SSL --> Conjunto de herramientas de criptografia que implementa los protocolos e red Secure Sockets Layer (SLLL v2/v3).
- HTTP --> sin encriptación
- HTTPS --> con encriptación
- CRLF --> salto de linea.
- Emulador --> MinTTY
- Bash --> Tipo de terminal que te permite hacer comandos de Linux en Windows

**Tabla de Comandos**

| Comando | Función |
| --- | --- |
| ls | Listar cosas |
| ls -a | Listar cosas incluso las ocultas |
| cd | Change drectory |
| git init | Crea un nuevo repositorio git o lo reinicializa |
| cat ~/.gitconfig | Muestra datos de usuario o de configuración en general |
| nano ~/.gitconfig | Variante de "code ~/gitconfig" para editar los datos de cat ~/.gitconfig |
| git commit -m | Hacer un informe de algún cambio |
| git log | Muestra tus datos del commit o algo así |
| git version | Muestra la versión actual de tu git |
| git --help | Muestra varios comandos y sus funciones |
| git config | Muestra varios comandos para realizar cambios en las configuraciones |
| git add | Añade un archivo al stagging area |
| git status | Muestra los changes to be commited y los unstracked files |
| git add . | Se añaden todos los archivos que esten al stagging area |
| / (pero recto) | Se usa para poner dos comandos en una misma linea |
| grep | Limitar la búsqueda a lo que se especifica a continuación |
| git log > report.txt | Guardar en un archivo los commits |
| git restore --staged (file) | Quitar un archivo |
|git checkout  (nombre de rama)| Cambia de rama |
|git branch (nombre)|Crea una rama|
|git branch -m (nuevo nombre)|Cambiar el nombre a una rama en la que estas|
|git branch -l|Listar todas las ramas|
|git branch -m (nombre de la rama) (nuevo nombre)|Cambiar el nombre a una rama desde otra|
|mkdir (nombre)|Crear una carpeta|
|touch (nombre)|Crear un archivo|
|git checkout -b (nombre)|Crear y moverse a una rama|
**Sobre commits**

- *Working Directory* --> Todavía no se ha hecho commit. ni se ha mandado un archivo para hacer un commit. Los archivos dentro de esta fase siempre estan en una "fase" untracked, es decir, que no tiene seguimiento.

- *Staging Area* --> Area temporal para enlistar los archivos y hacer el commit, es un área seguro en donde puedes pensar en si pasar el commit o no. Son archivos que seran parte del próximo commit, lo que le permite a git saber que cambios en el archivo se producirán para el **próximo comit** 

* *Repository* --> Cuando se hace el commit el archivo se almacena aquí

> Para ir del working directory al staging area se usa git add y del staging area al repository se usa git commit.
> Del staging area al working directory se usa rm --cached o git restore --staged

**Formalización de Commits**

- feat: añadimos algo nuevo que al usuario le va a servir 
- fix: solucionar o arreglar un bug o un defecto 	
- style: arreglar una tilde o quitar un ; o algo así 
- build: cambio relacionado al despliegue o dependencia 
	- calc@1.0.0 --> cal@1.1.1
- refactor: hacer mejores sobre el código para que sea optimizado y más entendible
- chore: que solo le sirve al programador y no al cliente

### Merge
1. ff --> Fast forward
2. no-ff -->Not fast forward
3. ff-only --> Only fast forward
4. rebase
5. squash

