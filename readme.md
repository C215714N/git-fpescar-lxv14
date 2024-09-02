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

## Remotos

corresponden a las direcciónes de los repositorios que se encuentran en algún servidor de GIT, como por ejemplo _github_. Podemos utilizar cualquiera de los siguientes comandos para editar esta configuración.

* __git remote add `remoto` `url`:__ agrega una dirección remota con la que podemos trabajar
* __git remote remove `remoto`__: elimina un remoto de la lista de direcciones
* __git remote rename `oldName` `newName`__: cambia el nombre del repositorio remoto
* __git remote set-url `remoto` `newUrl`__: Modifica la url de un repositorio remoto
* __git remote -v__: muestra la lista de direcciones y nombres de los repositorios remotos

## Colaboradores

Este proyecto fue desarrollado por los siguiente usuarios, que se encargaron de las distintas areas y participaron en la inclusion de las siguientes caracteristicas.

| Usuario | Correo | Area |
| maxiluma18 | [maxilucasmartinez18@gmail.com](mailto:maxilucasmartinez18@gmail.com) | Harry Footer |
| FedericoZapata | [federico11zapata@gmail.com](mailto:federico11zapata@gmail.com) | Logica Backend |
| C215714n | [cristiandracedo@hotmail.com](mailto:cristiandracedo@hotmail.com) | Navegacion |
| dantel8 | [dantelugo1505@gmail.com](mailto:dantelugo1505@gmail.com) | Logica |
| maxiluma19 | [maxilucasmartinez18@gmail.com](mailto:maxilucasmartinez18@gmail.com) | Harry Footer |
| diego-s10 | [dsena3472@gmail.com](mailto:dsena3472@gmail.com)|
| barbara1000 | [barbaranunez325@gmail.com](mailto:barbaranunez325@gmail.com)| Formulario|
| gabrieIsosa | [gabrielsosaeest1@gmail.com](mailto:gabrielsosaeest1@gmail.com) | Logica Javascript |
