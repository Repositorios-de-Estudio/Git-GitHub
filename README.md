# Curso: GIT+GitHub: Todo un sistema de control de versiones de cero
Curso de: [GIT+GitHub por Fernando Herrera](https://www.udemy.com/course/git-github/)


# CONCEPTOS Y DEFINICIONES

Git es un sistema de control de versiones distribuido, lo que significa que un clon local del proyecto es un repositorio de control de versiones completo. Estos repositorios locales plenamente funcionales permiten trabajar sin conexión o de forma remota con facilidad. Los desarrolladores confirman su trabajo localmente y, a continuación, sincronizan su copia del repositorio con la copia en el servidor. Este paradigma es distinto del control de versiones centralizado, donde los clientes deben sincronizar el código con un servidor antes de crear nuevas versiones.  \
**REF** [Que es Git: AzureDevOps](https://learn.microsoft.com/es-es/devops/develop/git/what-is-git)


## Repositorio Local
Copia local del repositorio (archivos de trabajo) por cada version nueva o cambios que se hayan hecho.Se puede trabajar con git de esta manera.

## Repositorio Distribuido
Copia del repositorio en un servidor externo de todos los archivos con todos los cambios realizados, esta es la manera como Git funciona. ej: GitHub, GitLab.

## Stage
Es el espacio de trabajo temporal donde se van guardando los cambios a los archivos con seguimiento. No estar en el stage sigfinica que los archivos en cuestion no tiene seguimiento.

## Commit
Se usa para para guardar el estado actual de todos los archivos en el stage sin cambios guardados. El commit es como un screenshot el cual se identifica mediante un hash y se pueden agregar comentarios a los commits.

Regresar a un commit anterior restauraria todos los archivos a ese estado y eliminaria los que no estan.

## Rama
Una rama o branch es una versión del repositorio desde un commit en especifico lo cual crea una bifurcación del repositorio el cual a su vez es como si fuera un repositorio a parte el cual sirve para realizar cambios para pruebas sin afectar la versión principal, luego se pueden introducir los cambios a otras ramas o a la rama principal.

La rama principal es: **main**

## CONFIGURACIÓN INICIAL

Configuración de usuario como información para los commits:

Usuario: \
`git config --global user.name "Mi Nombre"`

Correo: \
`git config --global user.mail "minombre@correo.com"`

Archivo configuraciones git: \
`~/.gitconfig`

Establecer rama por defecto de los repositorios inicializados:  \
`git config --global init.defaultBranch nombreRama` \
*Esto crea una rama llamada nombreRama, inicializa el repositorio y asigna la arama nombreRama como la principal.*

Información git del repositorio: \
`ProyectoCualquiera/.git` \
*Eliminar esta carpeta eliminaria git del proyecto*

Inicializar y agregar cambios: 
```
git init
git add .
git commit -m "Mi primer commit"
```

Archivo para omitir cambios: \
`Proyecto/.gitignore`

Cración de alias global para comandos: \
` git config --global alias.{alitas} "{comando y opciones}"`

ejemplo para usar `git s` como `git status --shot`:  \
` git config --global alias.s "status --short"`

**VER Y CAMBIAR CONFIGURACIÓN GLOBAL:** \
`git config --global -e`


***

## CONVENCIONES

1. **REQ:SG** = REQUIERE SEGUIMIENTO / REQUIERE SER AGREGADO AL STAGE

Significa que el archivo tuvo que haber sido agregado al control de cambios (git add), de lo contrario no se verá afectado por el comando en cuestion.

# COMANDOS DE GIT

uso de comandos con palabras compeltas: \
`git --palabra`

uso de comandos con abreviaciones: \
`git -abreviatura`

version git: \
`git --version`

ayuda de git: \
`git --help` \
`git --help palabra`

listar configuración: \
`git config --list`

eliminar alias: \
`git config --global --unset alias.{alias}`

estado del repositorio, modificaciones, eliminaciones y archvios que no estan en el satage: \
`git status`


git status con solo los cambios presentes: \
`git status --short` \
*Modificado: M* \
*Eliminados: D* \
*Sin seguimiento: ??, o que no esta en el satage*

ver ramas del repositorio: \
`git branch`

cambiar nombre de la rama: \
`git branch -m nombreActual nombreFuturo`

agregar cambios: \
`git add nombreArchivo`

agregar todos los cambios: \
`git add .`

agregar todos los cambios por tipo del directorio root: \
`git add *.html` \
*Esto NO es recurrente sobre los subdirectiorios*

agregar todos los cambios de un subdirectorio y su contenido: \
`git add carpeta/` \
*Esto SI es recurrente sobre los subdirectiorios*

agregar todos los cambios por tipo en un subdirectorio: \
`git add carpeta/*.html`

agregar todos los cambios y crear commit (REQ:SG): \
`git commit -am "commit"`

quitar archivo del stage: \
`git reset nombreArchivo`

descargar cambios sin haber hecho add . (REQ:SG): \
`git restore archivoNombre`

descartar todos los cambios sin haber hecho commit (REQ:SG): \
`git restore .`

regresar repositorio al commit anterior (REQ:SG): \
`git checkout -- .`

diferencia entre archivos estado actual vs ultimo commit:
`git diff` \
*archivo anterior: a/archivo* \
*archivo actual: b/archivo* \
*linea eliminada: - (en rojo)* \
*linea agreada: + (en verde)*

logs, ver los ultimos n registros:  \
`git log` \
`git log -n` \
`git log --oneline` \
*Se ven los commit realizados con su hash, su fecha, comentario y a donde apunta el HEAD, normelmente al main (HEAD -> main)*

logs con grafico para ver commits y ramas: \
`git log --oneline --decorate --all --graph`


## Agregar cambios y cargar al repositorio remoto
```
git add .
git commit -m "comentario"
git pull
```


# ERRORES COMUNES

- LF will be replaced by CRLF in archivoNombre, solución: \
`git config core.autocrlf true`

- Al revertir los cambios asegurarse de que todos los archivos esten en el stage para prevenir perder cambios nuevos. Puede ayudar crear una rama nueva con los cambios actuales.

# NOTAS
- Las carpetas vacias no se pueden agregar al stage
- Usar los alias facilita el trabajo

# RECOMENDACIONES
- Alistas s para status short: 
```
git config --global alias.s "status --short"
```
- Alistas lg para Log: Log, commit, fecha, mensaje, quien hizo el commit y a donde apunta el HEAD.
```
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
```


***
# REFERENCIAS
- [Documentación Oficial](https://git-scm.com/docs)


