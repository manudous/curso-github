> # 02 Más alla de los fundamentos de Git

>###  `- Diferencias entre commits y restauración de archivos`

Creamos un archivo README.md y lo incruimos esto dentro.

>> Pasos de instalación

Ejecutar

``
$ npm install
``

Y ejecutamos en la consola los siguientes comandos

- Inicializamos el proyecto.
``
$ git init
``
- Ver los cambios.
``
$ git s
``
- Agregamos los archivos para estar pendiente de los cambios.
``
$ git add -A
``
- Y hacemos un commit de ellos.
``
$ git commit -m "Creación del readme.md"
``

Modifiquemos el README e imaginemos que salimos a hacer algo, volvemos y no recordamos los cambios que hemos realizado, entonces ejecutamos el siguiente comando y sale una lista de las modificaciones que hemos realizado.

`
$ git diff
`
Si ya hemos realizado el stage, es decir subirlos con git add -A, si ejecutamos ese comando entonces no nos aparecería el listado deberíamos de ejecutar.

``
$ git diff --staged
``

Como puedo sacarlo del stagged

``
$ git reset HEAD README.md
``

Y si queremos revertir los cambios solo de este archivo podemos hacer

``
$ git checkout -- README.md
``

>###  `- Actualizar mensaje del commit y revertir commit`

Para que git añada al stage y haga un commit del archivo puedo hacer lo siguiente y me equivoque al poner el commit

``
$ git commit -am "Readme actualz"
``

Vamos a ver como podemos arreglarlo

``
$ git commit --amend -m "Actualizamos el readme"
``

Si se nos olvidó incluir los archivos que queríamos subir en este commit lo haríamos de la siguiente manera.

``
$ git reset --soft HEAD^
``
Haría un reset al último commit luego haríamos las modificaciones. Y agregaría otra vez mi subida al stage y mi commit

``
$ git commit -am "Actualizamos el readme con todos los archivos a omitir"
``

>> Puede aparecer un warning se soluciona con 

``
$ git config core.autocrlf true
``