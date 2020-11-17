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

``git reflog``

Y para regresar el punto que querramos hacemos.

``git reset --hard <punto de la historia>``