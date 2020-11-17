###  `- Viajes en el tiempo reset y reflog`

Vamos a introducir los archivos uno a uno y en cada uno de ellos vamos a hacer un stage y luego un commit con un mensaje para tenerlos referenciados.

Si queremos revertir en un determinado punto en nuestra historia pegamos la id de cuando editamos el archivo y ya le decimos que el cambio realizado no está en ningún commit. Realizamos ahora ese cambio que se nos olvidó y luego volvemos a hacer el commit.

``
$ git reset --mixed <punto de la historia>
``

Los archivos se quitaron del Stage pero no se eliminaron del commmit, para destruirlos y decir que no me interesa sería.

`` 
$ git reset --hard <punto de la historia>
``

Para ver todo el historial de git hacemos

``$ git reflog``

Y para regresar el punto que querramos hacemos.

``$ git reset --hard <punto de la historia>``

###  `- Cambiar el no mbre y eliminar archivos mediante git`

Creamos un archivo llamado destruir-mundo.txt, añadimos al stage y hacemos un commit

``$ git commit -am "Creando el archivo destruir el mundo"``

Como renombramos el archivo desde git

``$ git mv destruir-mundo.txt salvar-mundo.txt``

Hacemos un commit para subirlo.

Vamos ahora como eliminar el archivo, y ya lo mandamos al stage. Ahora tenemos que hacer el commit para estar seguro que lo vamos a Eliminar.

``$ git rm salvar-mundo.txt``

Ahora tenemos que hacer el commit para estar seguro que lo vamos a Eliminar.

``$ git commit -m "Borrando archivo salvar mundo"``

###  `- Cambiar el nombre y eliminar archivos mediante git`

Vamos hacer lo mismo pero fuera de git. Renombramos el archivo


```
- historia/superman.historia.md
+ historia/superman.md
```

Hacemos esto para actualizar y añademos al Stage

``$ git add -u``
``$ git add -A``

Y git ya me reconoce que hemos renombrado el archivo

```
M  READMEApuntes.md
R  historia/superman.historia.md -> historia/superman.md
``` 

Entonces hacemos el commit del archivo

```
git commit -m "Cambiamos el nombre de la historia de superman"
```

Ahora hacemos algo parecido con la eliminiación. Eliminamos el archivo con el editor. Hacemos git status para ver que el archivo todavía no está en el Stage. Actualizamos Y ya 

