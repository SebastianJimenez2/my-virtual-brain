---
annotation-target: git-cheat-sheet-education.pdf
---
# Diferencias
**Qué es Git?**
Informa cambios dentro de un código
**¿Qué es GitHub?**
Es un software con un algoritmo bastante potente, servicio que tenemos en la nube

| Git                                                  | GitHub                                                                                        |
| ---------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Sistema controlador de versiones                     | Plataforma de desarrollo                                                                      |
| Gestiona el historial de código                      | Cloud hosting y permite almacenar nuestra información en la nube, permitiendo la colaboración |
| Da un seguimiento de cambios realizados en el código | Es un repositorio para git, un gestor de proyectos de git que permite hostear el código local |
>[!Note]
>Los dos se complementan, pero NO son lo mismo
# Cosas sobre GIT 
- LFS (Large File Support) --> Se maneja mediante índices, que no se almacenan directamente en el repositorio.
- Open SSL --> Conjunto de herramientas de criptografía que implementa los protocolos e red Secure Sockets Layer (SLLL v2/v3).
- HTTP --> sin encriptación
- HTTPS --> con encriptación
- CRLF --> salto de línea.
- Emulador --> MinTTY
- Bash --> Tipo de terminal que te permite hacer comandos de Linux en Windows
# Cheat sheet
Git & GitHub sirven especialmente para una materia (u otras) [[_Diseño de software]] que se ve en quinto semestre.
![[git-cheat-sheet-education.pdf]]
# GitHub Flow
- *Working Directory* --> Todavía no se ha hecho commit. ni se ha mandado un archivo para hacer un commit. Los archivos dentro de esta fase siempre estan en una "fase" untracked, es decir, que no tiene seguimiento.
- *Staging Area* --> Area temporal para enlistar los archivos y hacer el commit, es un área seguro en donde puedes pensar en si pasar el commit o no. Son archivos que seran parte del próximo commit, lo que le permite a git saber que cambios en el archivo se producirán para el **próximo comit** 
* *Repository* --> Cuando se hace el commit el archivo se almacena aquí
>[!Note]
> Para ir del working directory al staging area se usa git add y del staging area al repository se usa git commit.
> Del staging area al working directory se usa rm --cached o git restore --staged
## Repositorios
- Local --> En mi computadora
- Remoto --> En la nube
## Commit
Es aquel que almacena la información cambiada dentro de un código. Adjunta: correo, nombre, fecha todo esto con una ID.
![](https://media.licdn.com/dms/image/v2/D5622AQGfX1xfIT-0YA/feedshare-shrink_1280/feedshare-shrink_1280/0/1715195271414?e=1751500800&v=beta&t=Yk_GYHV33nm3JbaHlisXSPW--svOiFhSQNPQO2HR4GI)
# Git branches
## Merging branches
## *Rebase*
Cómo unir una rama principal con una rama experimental
	- Rama experimental hacia rama main
## *Merge*
Permite hacer cambios mientras experimentas => pasar todo de la rama experimental en un cambio que engloba todo
### Fast forward (ff)
Es cuando se hace merge a partir de una rama que ha hecho cambios <mark style="background: #FF5582A6;">SIN QUE SE HAYAN HECHO CAMBIOS EN LA RAMA PRINCIPAL.</mark> Entonces, este merge solo une los cambios de la rama X a la principal <mark style="background: #FF5582A6;">SIN CREAR UN NUEVO COMMIT.</mark>
### Not fast forward (no-ff)
En esta forma se crean commits adicionales tanto en la rama main, como en la otra rama. En la rama main se muestra un commit "merge". Este es el commit más común al hacer PRs

![](https://i.sstatic.net/FMD5h.png)
### Rebase
Lo que hace rebase es básicamente hacer como si los commits de una rama X nacieron a partir del final de la rama principal. Imaginemos que partimos de A en main en una rama X y tenemos B => C, por otro lado, main sigue progresando y ahora tiene A => B => C, entonces lo que hace rebase es simular que los cambios que se hicieron en la rama X es la continuación, es decir los cambios B => C, se convertirán en D => E.
![](https://static.platzi.com/media/user_upload/rebase2-3bcb1804-1167-4d2f-af90-c7fed7a7fd6c.jpg)
>[!Warning]
>Rebasing cambios hará que se reescriba el historial del código. Por lo que no es sugerible hacerlo en grupos de trabajos amplios.

# Cherry pick
Consiste en tomar un commit en específico de una rama X para unirlo a la main, pero sin unir todos los cambios de esa rama en particular, sino específicamente uno en específico que solucione o arregle un error o bug específico en main.
![](https://media.geeksforgeeks.org/wp-content/uploads/20220302150549/AfterCherryPick.jpg)
También existen los siguientes métodos:
- ff-only
- squash
## Common branches en desarrollo

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc9baf1da-2154-49e3-b9d4-3620bfa6f6fb_1191x856.png)
# Conflictos
``` Python
<<<<<<<< HEAD
Cambios hechos en main      // Estos son los datos a agregar
========
Cambios hechos en rama X    // Contenido que ya existía
>>>>>>>> RAMA
```
# Tabla de Comandos

| Comando                                          | Función                                                                  |
| ------------------------------------------------ | ------------------------------------------------------------------------ |
| ls                                               | Listar cosas                                                             |
| ls -a                                            | Listar cosas incluso las ocultas                                         |
| cd                                               | Change drectory                                                          |
| git init                                         | Crea un nuevo repositorio git o lo reinicializa                          |
| cat ~/.gitconfig                                 | Muestra datos de usuario o de configuración en general                   |
| nano ~/.gitconfig                                | Variante de "code ~/gitconfig" para editar los datos de cat ~/.gitconfig |
| git commit -m                                    | Hacer un informe de algún cambio                                         |
| git log                                          | Muestra tus datos del commit o algo así                                  |
| git version                                      | Muestra la versión actual de tu git                                      |
| git --help                                       | Muestra varios comandos y sus funciones                                  |
| git config                                       | Muestra varios comandos para realizar cambios en las configuraciones     |
| git add                                          | Añade un archivo al stagging area                                        |
| git status                                       | Muestra los changes to be commited y los unstracked files                |
| git add .                                        | Se añaden todos los archivos que esten al stagging area                  |
| / (pero recto)                                   | Se usa para poner dos comandos en una misma linea                        |
| grep                                             | Limitar la búsqueda a lo que se especifica a continuación                |
| git log > report.txt                             | Guardar en un archivo los commits                                        |
| git restore --staged (file)                      | Quitar un archivo                                                        |
| git checkout  (nombre de rama)                   | Cambia de rama                                                           |
| git branch (nombre)                              | Crea una rama                                                            |
| git branch -m (nuevo nombre)                     | Cambiar el nombre a una rama en la que estas                             |
| git branch -l                                    | Listar todas las ramas                                                   |
| git branch -m (nombre de la rama) (nuevo nombre) | Cambiar el nombre a una rama desde otra                                  |
| mkdir (nombre)                                   | Crear una carpeta                                                        |
| touch (nombre)                                   | Crear un archivo                                                         |
| git checkout -b (nombre)                         | Crear y moverse a una rama                                               |
| git switch (rama)                                | Cambiarse de rama                                                        |
| git clean -df                                    | Eliminar archivos del área unstagged                                     |
| git ls-files                                     | Ver todos los archivos en stagging area                                  |
| git stash                                        | Almacenar cambios de un commit en el disco                               |
| git stash list                                   | Listar los stash creados                                                 |
| git stash drop (identifier)                      | Eliminar un stash específico                                             |
| git reflog                                       | Log de todos los cambios del proyecto incluyendo los commits borrados    |
# Conventional Commits
- feat: añadimos algo nuevo que al usuario le va a servir 
- fix: solucionar o arreglar un bug o un defecto 	
- style: arreglar una tilde o quitar un ; o algo así 
- build: cambio relacionado al despliegue o dependencia 
	- calc@1.0.0 --> cal@1.1.1
- refactor: hacer mejores sobre el código para que sea optimizado y más entendible
- chore: que solo le sirve al programador y no al cliente
# Eliminar commits
- `git reset --soft <comnmit>` => mantiene los cambios y vuelve al estado del commit
- `git reset --hard <comnmit>` => elimina los cambios y vuelve al estado del commit
>[!Warning]
>Tener cuidado con `--hard` ya que no se podrá recuperar lo que se haya borrado de ninguna forma
# Local to Remote
1. git init
2. git add .
3. git commit
4. git branch -M main
5. git remote add origin `<URL>`
6. git push -u origin main






























































>%%
>```annotation-json
>{"created":"2025-05-30T22:37:45.033Z","text":"Probando","updated":"2025-05-30T22:37:45.033Z","document":{"title":"git-cheat-sheet-education","link":[{"href":"urn:x-pdf:378d78094ee3afcd9aa56448d2631c29"},{"href":"vault:/Cursos/Git%20&%20GitHub/git-cheat-sheet-education.pdf"}],"documentFingerprint":"378d78094ee3afcd9aa56448d2631c29"},"uri":"vault:/Cursos/Git%20&%20GitHub/git-cheat-sheet-education.pdf","target":[{"source":"vault:/Cursos/Git%20&%20GitHub/git-cheat-sheet-education.pdf","selector":[{"type":"TextPositionSelector","start":1818,"end":1837},{"type":"TextQuoteSelector","exact":"INSTALLATION & GUIS","prefix":"Git commands for easy reference.","suffix":"With platform specific installer"}]}]}
>```
>%%
>*%%PREFIX%%Git commands for easy reference.%%HIGHLIGHT%% ==INSTALLATION & GUIS== %%POSTFIX%%With platform specific installer*
>%%LINK%%[[#^0dy5vz9c660b|show annotation]]
>%%COMMENT%%
>Probando
>%%TAGS%%
>#Sebas
^0dy5vz9c660b