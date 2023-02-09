# Curso: GIT+GitHub: Todo un sistema de control de versiones de cero
Curso de: [GIT+GitHub por Fernando Herrera](https://www.udemy.com/course/git-github/)


# DEFINICIÓN

Git es un sistema de control de versiones distribuido, lo que significa que un clon local del proyecto es un repositorio de control de versiones completo. Estos repositorios locales plenamente funcionales permiten trabajar sin conexión o de forma remota con facilidad. Los desarrolladores confirman su trabajo localmente y, a continuación, sincronizan su copia del repositorio con la copia en el servidor. Este paradigma es distinto del control de versiones centralizado, donde los clientes deben sincronizar el código con un servidor antes de crear nuevas versiones. ref [Que es Git: AzureDevOps](https://learn.microsoft.com/es-es/devops/develop/git/what-is-git)


## Repositorio Local
Copia local del repositorio (archivos de trabajo) por cada version nueva o cambios que se hayan hecho.

## Repositorio Distribuido
Copia del repositorio en un servidor externo de todos los archivos con todos los cambios realizados, esta es la manera como Git funciona. ej: GitHub, GitLab.

## Commit
Para guardar el estado actual de todos los archivos de un repositorio se hace con commit. El commit es como un screenshot.

## CONFIGURACIÓN INICIAL

Configuración de usuario como información para los commits:

Usuario:
    git config --global user.name "Mi Nombre"

Correo:
- git config --global user.mail "minombre@correo.com"

Ver configuración global: 
    git config --global -e

Archivo:
~/.gitconfig

Establecer rama por defecto de los repositorios inicializados: 
    git config --global init.defaultBranch nombreRama

Información git del repositorio:
    ProyectoCualquiera/.git

Inicializar: 
    git init

Archivo para omitir cambios:
    modificar Proyecto/.gitignore



# COMANDOS DE GIT

uso de comandos con palabras compeltas: git --palabra
uso de comandos con abreviaciones: git -abreviatura
version git: git --version
ayuda de git: git --help , git --help palabra

estado del repositorio, archivos pendientes de seguimiento: git status

agregar cambios: git add nombreArchivo
agregar todos los cambios: git add .

quitar archivo de seguimiento: git reset nombreArchivo

descargar cambios sin haber hecho add . : git restore archivoNombre
descartar todos los cambios sin haber hecho commit: git restore .

regresar repositorio al commit anterior: git checkout -- .




## Agregar cambios y cargar al repositorio remoto

git add .
git commit -m "comentario"
git pull


# ERRORES COMUNES

LF will be replaced by CRLF in archivoNombre, solución:
git config core.autocrlf true


***
# REFERENCIAS


