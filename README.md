# Curso: GIT+GitHub: Todo un sistema de control de versiones de cero
Curso de: [GIT+GitHub por Fernando Herrera](https://www.udemy.com/course/git-github/)


# CONCEPTOS Y DEFINICIONES

Git es un sistema de control de versiones distribuido, lo que significa que un clon local del proyecto es un repositorio de control de versiones completo. Estos repositorios locales plenamente funcionales permiten trabajar sin conexión o de forma remota con facilidad. Los desarrolladores confirman su trabajo localmente y, a continuación, sincronizan su copia del repositorio con la copia en el servidor. Este paradigma es distinto del control de versiones centralizado, donde los clientes deben sincronizar el código con un servidor antes de crear nuevas versiones. 
**REF** [Que es Git: AzureDevOps](https://learn.microsoft.com/es-es/devops/develop/git/what-is-git)


## Repositorio Local
Copia local del repositorio (archivos de trabajo) por cada version nueva o cambios que se hayan hecho.Se puede trabajar con git de esta manera.

## Repositorio Distribuido
Copia del repositorio en un servidor externo de todos los archivos con todos los cambios realizados, esta es la manera como Git funciona. ej: GitHub, GitLab.

## Commit
Para guardar el estado actual de todos los archivos de un repositorio se hace con commit. El commit es como un screenshot.

## Rama
Una rama o branch es una versión del repositorio desde un commit en especifico lo cual crea una bifurcación del repositorio el cual a su vez es como si fuera un repositorio a parte el cual sirve para realizar cambios para pruebas sin afectar la versión principal, luego se pueden introducir los cambios a otras ramas o a la rama principal.

La rama principal es: main

## CONFIGURACIÓN INICIAL

Configuración de usuario como información para los commits:

Usuario:
`git config --global user.name "Mi Nombre"`

Correo:
`git config --global user.mail "minombre@correo.com"`

Ver configuración global: 
`git config --global -e`

Archivo configuraciones git:
`~/.gitconfig`

Establecer rama por defecto de los repositorios inicializados: 
`git config --global init.defaultBranch nombreRama`

*Esto crea una rama llamada nombreRama, inicializa el repositorio y asigna la arama nombreRama como la principal.*

Información git del repositorio:
ProyectoCualquiera/.git

Inicializar y agregar cambios: 
`git init`
`git add .`
`git commit -am "Mi primer commit"`

Archivo para omitir cambios:
modificar Proyecto/.gitignore

## CONVENCIONES

**REQ:SG** = REQUIERE SEGUIMIENTO

- Requiere seguimiento significa que el archivo tuvo que haber sido agregado (git add) al control de cambios de git, de lo contrario no se verá afectado por el comando en cuestion.

# COMANDOS DE GIT

uso de comandos con palabras compeltas:
`git --palabra`

uso de comandos con abreviaciones:
`git -abreviatura`

version git:
`git --version`

ayuda de git:
`git --help`
`git --help palabra`

estado del repositorio, archivos pendientes de seguimiento:
`git status`

ver ramas del repositorio:
`git branch`

cambiar nombre de la rama:
`git branch -m nombreActual nombreFuturo`

agregar cambios:
`git add nombreArchivo`

agregar todos los cambios:
`git add .`

agregar todos los cambios y crear commit (REQ:SG):
`git commit -am "commit"`

quitar archivo de seguimiento:
`git reset nombreArchivo`

descargar cambios sin haber hecho add . (REQ:SG):
`git restore archivoNombre`

descartar todos los cambios sin haber hecho commit (REQ:SG):
`git restore .`

regresar repositorio al commit anterior (REQ:SG):
`git checkout -- .`


logs, ver los ultimos n registros: 
`git log`
`git log -n`
*Se ven los commit realizados con su hash, su fecha, comentario y a donde apunta el HEAD, normelmente al main (HEAD -> main)*




## Agregar cambios y cargar al repositorio remoto

`git add .`
`git commit -m "comentario"`
`git pull`


# ERRORES COMUNES

LF will be replaced by CRLF in archivoNombre, solución:
`git config core.autocrlf true`


Al revertir cambios asegurarse de que todos los archivos tengan seguimiento para prevenir perder cambios nuevos. Puede ayudar crear una rama nueva con los cambios actuales.

# NOTAS
- Las carpetas vacias no se pueden agregar al seguimiento

***
# REFERENCIAS


