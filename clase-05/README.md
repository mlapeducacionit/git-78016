# Clase 05 - Git Desarrollador Colarativo

## Ayuda de Git Stash

```sh
git stash --help
```

## Alias de GIT
Me permite crear alias de comandos para en vez de estar escribiendo el comando y sus subcomandos hacerlo en forma resumida (corta). A través de una letra o una palabra.

### Creo un alias

```sh
git config --global alias.<alias-elegido> "<comando-de-git-sin-la-palabra-git>"
git config --global alias.l "log --oneline"
git config --global alias.ll "log --oneline --all --graph --decorate"
git config --global alias.s "status --short"
git config --global alias.c "commit -m"
```

### Quitar alias

```sh
git config --global --unset alias.ll # Me quita el alias ll
```

### Listar alias configurados

```sh
git config --global --get-regexp alias
```

## GIT RESET
Me permite desahacer un commit o commits (cambios) en el repositorio. Los cambios deshechos se van a colocar en el área de trabajo o el área de staging (index).

### 3 tipos de resets

* Git Reset Soft
* Git Reset Mixed (default)
* Git Reset Hard 

1. Git Reset Soft
Va a borrar el commit o los commits seleccionados y arrojar los cambios al staging area (index)

![soft](_ref/soft.png)

```sh
git reset --soft <hash>
```

2. Git Reset Mixed (default)
Va a borrar el commit o los commits seleccionados y arrojar el contenido de esos commits dentro del área de Working Directory

![mixed](_ref/mixed.png)

```sh
git reset <hash>
git reset --mixed <hash>
```

3. Git Reset Hard **CUIDADO**
Va a borrar el commit o los commits seleccionados y descarta el contenido. O sea los cambios se pierden.

![hard](_ref/hard.png)

```sh
git reset --hard <hash>
```

## Trabajo con ramas locales y remotas

### Actualiza la metada para ver si hay cambio o ramas que en mi repo no veo

```sh
git fetch
```

### Listo ramas locales

```sh
git branch
```

### Listo ramas remotas

```sh
git branch -r
```

### Listo ramas remotas y locales

```sh
git branch -a
```

### Listo ramas remotas/locales con detalle

```sh
git branch -av
```

### Borrar una rama remota

```sh
git push origin --delete <nombre-rama>
git push origin --delete feature/ramas
```

# GITHUB CLI
Es una herramienta de consola para automatizar tareas de administración de GitHub.

<https://cli.github.com/>

# Git Cherry Pick
Permite selecionar un commit o varios de manera independiente y colocarlos en otra rama.

## Selecciono un único commit 

```sh
git cherry-pick <hash>
```

## Seleciono varios commits con extremos incluidos

```sh
git cherry-pick <hash>^..<hash>
```

## Seleciono varios commits sin extremos

```sh
git cherry-pick <hash>..<hash>
```

## Git Tag
Me permite marcas ciertos commits y darles un indentificador especial. Lo que es marcas ciertos commits con una etiqueta
