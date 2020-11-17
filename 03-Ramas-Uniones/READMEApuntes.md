> ## Ramas, Uniones, Conflictos y tags

Son ramas de tiempo son líneas del tiempo alternativas las cuales van a poder modificar sin afectar la rama principal que eventualmente puede reincorparse al máster. Pueden existir diferentes panoramas como por ejemplo cuando chocan, por decir algo, hay conflictos y no se pueden unir de forma limpia y lo que hace git para resolverlo por ejemplo con con flashforward, resoluciones automáticas y en algunos casos hacerlo manualmente.

Creamos un nuevo archivo

`villanos.md`

y lo rellenamos con 

```
# Villanos

1. Lex Luthor
2. Joker
```

Pero ahora queremos hacer una rama a parte para seguir modificándolo. Siguiendo con el ejemplo añadimos como nombre de rama, rama-villanos

```
$ git branch <nombre rama>
```

Para saber las ramas que tenemos

```
$ git branch
```

Cuando queremos hacer a otra rama tenemos que hacer un checkout

```
$ git checkout rama-villanos
```

Agregamos cosas a esta nueva rama y ahora pensamos que vamos a agregar al máster pq están bien las cosas.

Vemos las modificaciones de una rama y otra
```
$ git diff rama-villanos master
```
Regresamos al máster para volver al master

```
$ git checkout master
```

Y unimos ambas ramas con merge

```
$ git merge rama-villanos
```