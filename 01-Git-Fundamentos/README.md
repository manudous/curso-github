> ## 01 Fundamentos de Git

En git los proyectos se llaman repositorios. Existen dos maneras principales de como se manejan los repositorios.

- Repositorio Central: Nuestro equipo de trabajo trabaja directamente en un servidor.

- Repositorio Destribuido: Todo nuestro equipo de trabajo tiene una copia tal cual del repositorio, así es como trabaja Git.

>###  `- Primeros Comandos -git config -git help`

Vamos a configurar primero el git para saber quién utiliza nuestro git.

`
$ git config --global user.name "Manudous"
`

Y otro para el correo.

`
$ git config --global user.email "manudous@gmail.com"
`

Le estoy diciendo a Git que cada vez que alguien en esta máquina haga un commit va a grabarlo con el nombre de Manudous y el correo `manudous@gmail.com.`

Como podemos ver donde están esos registros
```
$ git config --global -e
```
>###  `- Iniciando un proyecto y creando un repositorio`
Utilizaremos este proyecto de Bootstrap que se encuentra en este directorio. Entramos en la consola dentro de la carpeta donde está el proyecto.
Para inicializar este proyecto y decirle a git que se cree un repositorio donde vamos a empezar a trabajar le decimos lo siguiente. Nos crea un repositorio local en una carpeta oculta llamada .git.

`
$ git init
`

Hay otro comando git status que te saca todos los archivos que sabe que están en esa carpeta pero no han sido registrada en otro lugar. 

`
$ git status
`

Voy a decirle a git que quiero agregar todos los archivos para que esté pendiente de los cambios.

`
$ git add .
`

Si quisieramos agregar un archivo lo haríamos de la siguiente manera

`
$ git add README.md
`

Si ahora queremos que Git haga una fotografía del proyecto como lo tenemos ahora mismo. Pero va a pedir un mensaje que debemos introducírselo.

`
$ git commit -m "Primer commit"
`
>###  `- ¿Qué hace git por nosotros en estos momentos?`

Si diera la casualidad que borrarmos parte del proyecto y lo guardaramos, la forma para recuperarlo sería la siguiente.

`
$ git commit checkout -- .
`

Vemos otra cosa más extremas, borramos el estilo del bootstrap, y borramos la carpeta de JavaScript accidentalmente. Para recuperar como estaba ejecutamos este comando y se va a recuperar como estaban los archivos antes de nuestro último commit.

Si queremos ver los commits que hemos realizado ejecutamos

`
$ git log
`

Y los commits nos aparecen ordenados del más reciente al más antiguo. Nos aparece todos los datos quién lo creo, cuando se creo y el mensaje que introducimos en el commit.

Si se presenta un error con el CRLF por la consola, no es nada serio, es básicamente una interpretación de un caracter. Simplemente se ejecuta esto:

`
$ git config core.autocrlf true
`

>###  `- Diferentes formas de agregar archivos en el escenario`

Supongamos ahora que no queremos hacer un commit con todos los archivos, como hacemos eso. Si queremos agregar todos los archivos con alguna estensión en concreto.

`
$ git add *.png
`

Si quisieramos subir una carpeta.

`
$ git add css/
`

Si queremos subir todos los archivos menos uno. Primero subimos todos los archivos que fueron modificados.

`
$ git add -A
`

Y luego excluimos ese archivo, esta extensión o esa carpeta.

`
$ git reset *.xml
`

>> ##### Otros comandos para agregar archivos

- Agrega todos los txt del TODO el proyecto

`
$ git add "*.txt"
`

- Agrega todos los txt en el directorio actual

`
$ git add *.txt
`

- Agrega todos los archivos que se hayan modificado

`
$ git add --all
`

- Agrega los archivos que listemos

`
$ git add <lista de archivos>
`

- Agrega todos los PDFs dentro de la carpeta PDFs

`
$ git add pdfs/* .pdf
`

- Agrega todos los archivos dentro de la carpeta PDFs

`
$ git add pdfs/
`

>###  `- Otras formas de revisar el log y los cambios desde el último commit`

Cuando hacemos un git log aparecen todos los commits que hemos realizado, arriba aparece el HEAD, se refiere al último commit de la rama actual.
Si quiremos saber solo el hash corto y el mensaje que introducimos en ese commit ejecutamos

`
$ git log --oneline
`

Pero se recomiendo que se haga de la siguiente manera que se verá todo mucho mejor. Se verá mucho mejor cuando el projecto se vaya haciendo cada vez más grande.

`
$ git log --oneline --decorate --all --graph
`

Si queremos quitar también datos innecesario cuando hacemos un git status y saber en la rama que estamos trabjando, podemos hacer.

`
$ git status -s -b
`

###  `- Creando Alias para nuestros Comandos`

Posemos un pequeño sinónimos para cuando escribamos todo el comando con todos los modificadores que les pusimos. Lo creamos de la siguiente manera.

`
$ git config --global alias.lg "log --oneline --decorate --all --graph"
`

Ahora cuando escribamos git lg me hará lo mismo que escribir git log --oneline --decorate --all --graph

`
$ git lg
`

Otro que vamos a agregar va a ser el alias del status

`
$ git config --global alias.s "status -s -b"
`

Y ahora ejecutaríamos

`
$ git s
`

Recuerden que toda la información que grabamos en el local se encuentra aquí para abrir el archivo ahí están todos nuestros alias.

`
$ git config --global -l
`

Es más seguro que git config --global -e, pq estamos en modo lectura y no en modo escritura. Si estamos en un editor se abre un archivo llamado .gitconfg. Con el parámetro -e.


