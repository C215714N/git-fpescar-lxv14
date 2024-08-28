# Git Desarrollo Colaborativo

Esto es una guia para los alumnos de la capacitacion de __sistemas de control de versiones__ que cursan los dias _lunes miercoles y viernes de 14hs a 17hs_

## Areas de GIT

* __Working Directory__: Corresponde a la carpeta donde inicializamos el repositorio, muy rara vez utilizaremos la consola por aqui.
* __Staging Area (INDEX)__: El area de control de cambios es la encargada de realizar el seguimiento a los archivos del proyecto, aqui se realizan las capturas (SNAPSHOT)
* __Repository (Local)__: El almacen local, corresponde a la carpeta donde se guardan las capturas en formato BLOB, utilizan una estructura hexadecimal.

## Configuracion Inicial

Antes de comenzar a trabajar en un proyecto es importante que configuremos nuestro nombre de usuario y correo con el que seremos identificados en los diferentes proyectos. Para ello utilizaremos los siguientes comandos

```sh
    git config --global user.name "username"
    git config --global user.email "user@server"
```