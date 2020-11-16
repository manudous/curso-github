> ## 01 Fundamentos de Git

En git los proyectos se llaman repositorios. Existen dos maneras principales de como se manejan los repositorios.

- Repositorio Central: Nuestro equipo de trabajo trabaja directamente en un servidor.

- Repositorio Destribuido: Todo nuestro equipo de trabajo tiene una copia tal cual del repositorio, así es como trabaja Git.

>###  `- Primeros Comandos -git config -git help`

Vamos a configurar primero el git para saber quién utiliza nuestro git
```
$ git config --global user.name "Manudous"
```
Y otro para el correo
```
$ git config --global user.email "manudous@gmail.com"
```
Le estoy diciendo a Git que cada vez que alguien en esta máquina haga un commit va a grabarlo con el nombre de Manudous y el correo `manudous@gmail.com.`

Como podemos ver donde están esos registros
```
$ git config --global -e
```
>###  `- Iniciando un proyecto y creando un repositorio`
Utilizaremos este proyecto de Bootstrap que se encuentra en este directorio. Entramos en la consola dentro de la carpeta donde está el proyecto.
Para inicializar este proyecto y decirle a git que se cree un repositorio donde vamos a empezar a trabajar le decimos lo siguiente.
```
$ git init
```

Hay otro comando git status que te saca todos los archivos que sabe que están en esa carpeta pero no han sido registrada en otro lugar.
```
$ git init
```
Voy a decirle a git que quiero agregar todos los archivos para que esté pendiente de los cambios.
```
$ git add .
```
Si ahora queremos que Git haga una fotografía del proyecto como lo tenemos ahora mismo. Pero va a pedir un mensaje que debemos introducírselo.
```
$ git commit -m "Primer commit"
```
>###  `- ¿Qué hace git por nosotros en estos momentos?`

Si diera la casualidad que borrarmos parte del proyecto y lo guardaramos, la forma para recuperarlo sería la siguiente.
```
$ git commit checkout -- .
```
Vemos otra cosa más extremas, borramos el estilo del bootstrap, y borramos la carpeta de JavaScript accidentalmente. Para recuperar como estaba ejecutamos este comando y se va a recuperar como estaban los archivos antes de nuestro último commit.



