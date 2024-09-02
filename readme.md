# Git Desarrollo Colaborativo

Esto es una guia para los alumnos de la capacitacion de **sistemas de control de versiones** que cursan los dias _lunes miercoles y viernes de 14hs a 17hs_

## Areas de GIT

- **Working Directory**: Corresponde a la carpeta donde inicializamos el repositorio, muy rara vez utilizaremos la consola por aqui.
- **Staging Area (INDEX)**: El area de control de cambios es la encargada de realizar el seguimiento a los archivos del proyecto, aqui se realizan las capturas (SNAPSHOT)
- **Repository (Local)**: El almacen local, corresponde a la carpeta donde se guardan las capturas en formato BLOB, utilizan una estructura hexadecimal.

## Configuracion Inicial

Antes de comenzar a trabajar en un proyecto es importante que configuremos nuestro nombre de usuario y correo con el que seremos identificados en los diferentes proyectos. Para ello utilizaremos los siguientes comandos

```sh
    git config --global user.name "username"
    git config --global user.email "user@server"
```

## Remotos

corresponden a las direcciónes de los repositorios que se encuentran en algún servidor de GIT, como por ejemplo _github_. Podemos utilizar cualquiera de los siguientes comandos para editar esta configuración.

- **git remote add `remoto` `url`:** agrega una dirección remota con la que podemos trabajar
- **git remote remove `remoto`**: elimina un remoto de la lista de direcciones
- **git remote rename `oldName` `newName`**: cambia el nombre del repositorio remoto
- **git remote set-url `remoto` `newUrl`**: Modifica la url de un repositorio remoto
- **git remote -v**: muestra la lista de direcciones y nombres de los repositorios remotos

## Colaboradores

Este proyecto fue desarrollado por los siguiente usuarios, que se encargaron de las distintas areas y participaron en la inclusion de las siguientes caracteristicas.
<!-- |-|-|-| no borren esa linea. -->
| Usuario | Correo | Area |
|-|-|-|
| maxiluma18 | [maxilucasmartinez18@gmail.com](mailto:maxilucasmartinez18@gmail.com) | Harry Footer |
| Diana2754 | [dianacc.alali@gmail.com] (mailto:dianacc.alali@gmail.com) | 
| FedericoZapata | [federico11zapata@gmail.com](mailto:federico11zapata@gmail.com) | Logica Backend |
| C215714n | [cristiandracedo@hotmail.com](mailto:cristiandracedo@hotmail.com) | Navegacion |
| 2Oraclos4 | [omar.spinetta12@gmail.com](mailto:omar.spinetta12@gmail.com) |
| dantel8 | [dantelugo1505@gmail.com](mailto:dantelugo1505@gmail.com) | Logica |
| diego-s10 | [dsena3472@gmail.com](mailto:dsena3472@gmail.com)|
| barbara1000 | [barbaranunez325@gmail.com](mailto:barbaranunez325@gmail.com)| Formulario|
| gabrieIsosa | [gabrielsosaeest1@gmail.com](mailto:gabrielsosaeest1@gmail.com) | Logica Javascript |
| LautiCabrera | [lauti.cabrera114@gmail.com](mailto:lauti.cabrera114@gmail.com) | Logica Javascript |
<<<<<<< HEAD
| AgustinNazaretto | [agustin_nazaretto@hotmail.com](mailto:agustin_nazaretto@hotmail.com)| Footer|
=======
>>>>>>> 0acfe0e64b7a2329142fc24c3405ae31d992887f
| LeiFraz | [Flajarkin99@hotmail.com](Flajarkin99@hotmail.com) | Logica Backend |
