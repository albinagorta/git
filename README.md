# LOS 3 ESTADOS DE GIT
-- Espacio de trabajo
-- Área de preparación
-- Repositorio (Carpeta .git) 


-- ver estados de los archivos
> git status

-- agregar al Área de preparación
> git add .

-- crear un comentario en Área de preparación
> git commit -m "nuevo comentario"

-- Con este comando podemos saltar el área de preparación.
> git commit -a -m "mensaje del commit"


-- subir a repositorio
> git push origin nombrerama

--almacenar temporalmente
> git stash

--aplicar los cambios ocultos temporalmente
> git stash apply

-- Quitar archivos del área de preparación a espacio de trabajo
> git restore --staged nombrearchivo

-- Deshaciendo cambios realizados por unidad
> git checkout nombrearchivo

-- Deshaciendo cambios realizados todos
> git checkout -f

-- Comparar cambios reposito vs espacio de trabajo detallado
> git diff nombrearchivo

-- Comparar cambios reposito vs espacio de trabajo resumido
> git diff --stat nombrearchivo


-- Con este comando vinculamos nuestro repositorio local con Github.
> git remote add origin https://github.com/usuario/proyecto-xyz.git

-- deshacer cambios por archivo local
> git reset <fichero>

-- deshacer todos los cambios local
> git reset --hard

-- deshacer por commit 
>git reset --hard <commit>


-- Patrones de nombres de archivos que git ignorará.
.gitignore


# RAMAS START 

-- crear nueva rama y posicionarte 
-- Método de 2 pasos
> git branch NOMBRE-NUEVA-RAMA
> git checkout NOMBRE-NUEVA-RAMA

-- Atajo
> git checkout -b NOMBRE-NUEVA-RAMA


-- Renombrar una Rama
> git branch -m VIEJO-NOMBRE-RAMA NUEVO-NOMBRE-RAMA

-- Alternativa
> git branch --move VIEJO-NOMBRE-RAMA NUEVO-NOMBRE-RAMA


-- posicionarte en una rama
> git switch nombrerama

-- ver lista de ramas
> git branch

-- agrupar las ramas a master para eso primero es posicionase en master y ejecutar
> git merge nombreramaagrupar


-- eliminar una rama
> git branch -d RAMA-A-ELIMINAR

-- Alternativa:
> git branch --delete RAMA-A-ELIMINAR


-- Nos muestra cuáles ramas no han sido fusionadas a la rama actual.
> git branch --no-merged

-- Nos muestra las ramas que han sido fusionadas a la rama actual.
> git branch --merged


-- eliminar las ramas para eso primero es posicionase en master y ejecutar
> git push --delete origin nombrerama


Ayuda con Ramas de Git

> git help branch
> git branch --help
> man git-branch

# RAMAS END 


# HISTORIAL DE COMMITS START
-- ver seguimiento de ramas
> git log --oneline --all --graph --decorate

-- Muestra todo el historial de commits del proyecto
> git log

-- Muestra el historial con el formato que indicamos.
> git log --pretty=format:"%h - %an, %ar : %s"


-- Limitar la salida del historial
> git log -n: Cambiamos la n por cualquier número entero, por ejemplo: `git log -2` nos mostrará los 2 commits más recientes.
#
> git log --after="2016-04-07 00:00:00": Muestra los commits realizados después de la fecha especificada.
#
> git log --before="2016-04-08 00:00:00": Muestra los commits realizados antes de la fecha especificada.

-- Las banderas del comando `git log` se pueden usar juntas según son convenga, por ejemplo:
> git log --after="2016-04-07 12:00:00" --before="2016-04-07 12:30:00"

-- Este comando nos muestra el historial en una sola línea por commit.
> git log --oneline

# HISTORIAL DE COMMITS END


# ETIQUETA START

-- Lista las etiquetas en orden alfabético.
> git tag nombre_etiqueta

-- Etiqueta anotada. Se guarda en la base de datos de Git como un objeto entero. Tiene un checksum; contiene el nombre del etiquetador, correo electrónico y fecha; y tienen un mensaje asociado.
> git tag -a nombre_etiqueta -m "mensaje de la etiqueta"


-- Lista las etiquetas que coincidan con el patrón especificado.
> git tag -l "v1.*"

# ETIQUETA END


# RENOMBRAR ARCHIVOS DE GIT 

-- Renombrar archivos
> git mv file_from file_to


-- Equivalente a los siguientes pasos:
1. Renombrar el archivo manualmente
2. `git rm` para eliminar el archivo con git.
3. `git add` para agregar el archivo con el nuevo nombre. 

