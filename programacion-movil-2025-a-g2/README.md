# Guía Básica de Git

## Configuración Inicial
Al empezar, asegúrate de configurar tu usuario en Git:

```sh
#  Configurar el usuario y correo
git config --global user.name "TuNombre"
git config --global user.email "tuemail@example.com"
```

---

## Iniciar un Repositorio

```sh
#  Crear un nuevo repositorio local
git init
```

---

## Clonar un Repositorio
Para trabajar en un proyecto existente:

```sh
#  Clonar un repositorio
git clone https://github.com/usuario/repositorio.git
```

---

## Estados Básicos en Git

```sh
#  Ver el estado actual de los archivos
git status

#  Agregar un archivo específico al área de preparación
git add archivo.txt

#  Agregar todos los archivos modificados
git add .
```

---

## Realizar un Commit

```sh
#  Confirmar los cambios con un mensaje descriptivo
git commit -m "Descripción del cambio"
```

---

## Subir Cambios al Repositorio Remoto (Push)

```sh
#  Enviar los cambios a la rama principal del repositorio remoto
git push origin main
```

Si es la primera vez que haces push en una rama nueva:

```sh
#  Subir una nueva rama
git push --set-upstream origin nombre-rama
```

---

## Descargar Cambios del Repositorio (Pull)

```sh
#  Obtener cambios y fusionarlos automáticamente
git pull origin main
```

---

## Manejo de Ramas

```sh
#  Ver todas las ramas locales
git branch

#  Crear una nueva rama
git branch nombre-rama

#  Cambiar a otra rama
git checkout nombre-rama

#  Crear y cambiar a una nueva rama en un solo comando
git checkout -b nombre-rama
```

---

## Fusionar Ramas

```sh
#  Cambiar a la rama principal
git checkout main

#  Fusionar cambios de otra rama
git merge nombre-rama
```

---

## Eliminar Ramas

```sh
#  Eliminar una rama local
git branch -d nombre-rama

#  Eliminar una rama en el repositorio remoto
git push origin --delete nombre-rama
```

---

## Eliminar Archivos

```sh
#  Eliminar un archivo localmente
git rm archivo.txt

#  Confirmar la eliminación
git commit -m "Archivo eliminado"

#  Enviar los cambios al repositorio remoto
git push origin main
```

Para eliminar un archivo en el repositorio remoto (después de eliminarlo localmente y hacer push):

```sh
#  Eliminar un archivo en el repositorio remoto
git push origin --delete archivo.txt
```

---

## Resolver Conflictos
Si hay conflictos al hacer un `merge` o `pull`, Git te pedirá que resuelvas manualmente los archivos en conflicto. Luego:

```sh
#  Marcar los archivos como resueltos
git add archivo_resuelto.txt

#  Crear un commit después de resolver conflictos
git commit -m "Conflictos resueltos"
```

---

## Ver el Historial de Cambios

```sh
#  Ver historial de commits
git log --oneline --graph --all
```

