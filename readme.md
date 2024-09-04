# Git Desarrollo Colaborativo

Esto es una guia para los alumnos de la capacitacion de **sistemas de control de versiones** que cursan los dias _lunes miercoles y viernes de 14hs a 17hs_

## Areas de GIT

- **Working Directory**: Corresponde a la carpeta donde inicializamos el repositorio, muy rara vez utilizaremos la consola por aqui.
    * __git init__: inicializa el repositorio de git
    * __git config user.name `<username>`__: define el nombre de usuario para el repositorio.
    * __git config user.email `<email>`__: establece el correo de contacto para el repositorio.
    * __rm -rf `.git`__ elimina el repositorio de git
- **Staging Area (INDEX)**: El area de control de cambios es la encargada de realizar el seguimiento a los archivos del proyecto, aqui se realizan las capturas (SNAPSHOT)
    * __git status__: muestra el estado de los archivos comparandolos con la ultima captura de codigo realizada.
    * __git diff__: muestra las diferencias de codigo con respecto a la ultima captura registrada en el INDEX
    * __git add `<file>`__: agrega los cambios del archivo al area de control de cambios mediante una captura.
- **Repository (Local)**: El almacen local, corresponde a la carpeta donde se guardan las capturas en formato BLOB, utilizan una estructura hexadecimal.
    * __git commit__: abre el editor para emitir una confirmacion de los cambios realizados.
    * __git log__: muestra el registro de confirmaciones realizadas en formato de commits.
    * __git push__: envia los cambios locales a la rama correspondiente de repositorio remoto.

## Configuracion Inicial

Antes de comenzar a trabajar en un proyecto es importante que configuremos nuestro nombre de usuario y correo con el que seremos identificados en los diferentes proyectos. Para ello utilizaremos los siguientes comandos

```sh
    git config --global user.name "username"
    git config --global user.email "user@server"
```

## Remotos

corresponden a las direcciónes de los repositorios que se encuentran en algún servidor de GIT, como por ejemplo _github_. Podemos utilizar cualquiera de los siguientes comandos para editar esta configuración.

- **git remote add `remoto` `url`**: agrega una dirección remota con la que podemos trabajar
- **git remote remove `remoto`**: elimina un remoto de la lista de direcciones
- **git remote rename `oldName` `newName`**: cambia el nombre del repositorio remoto
- **git remote set-url `remoto` `newUrl`**: Modifica la url de un repositorio remoto
- **git remote -v**: muestra la lista de direcciones y nombres de los repositorios remotos

## Apuntadores

Existen diferentes referencias de posicion en el historial de cambios y se utilizan para identificar y navegar entre diferentes commits, ramas y otros objetos en el repositorio. Entre los apuntadores mas comunes se encuentran

* __HEAD__: Apuntador movil, que indica al usuario donde se encuentra dentro del repositorio.
* __BRANCH__: Apuntador dinamico, que siempre apunta al ultimo commit de la linea de tiempo actual.
* __TAG__: Apuntador estatico, que se corresponde con algun commit en particular y es utilizado para el versionado.
* __STASH__: Apuntador de la zona temporal, ideal cuando necesitamos cambiar de rama y tenemos cambios pendientes.

## Colaboradores

Este proyecto fue desarrollado por los siguiente usuarios, que se encargaron de las distintas areas y participaron en la inclusion de las siguientes caracteristicas.

| Usuario | Correo | Area |
|-|-|-|
| maxiluma18 | [maxilucasmartinez18@gmail.com](mailto:maxilucasmartinez18@gmail.com) | Harry Footer |
| Diana2754 | [dianacc.alali@gmail.com](mailto:dianacc.alali@gmail.com) | 
| ezevallelugo | [eze0072@gmail.com](mailto:eze0072@gmail.com) | Logica Backend |
| FedericoZapata | [federico11zapata@gmail.com](mailto:federico11zapata@gmail.com) | Logica Backend |
| C215714n | [cristiandracedo@hotmail.com](mailto:cristiandracedo@hotmail.com) | Navegacion |
| tomasroetti |[roettitomas@gmail.com](mailto:roettitomas@gmail.com) | Creacion de las cards |
| 2Oraclos4 | [omar.spinetta12@gmail.com](mailto:omar.spinetta12@gmail.com) |
| dantel8 | [dantelugo1505@gmail.com](mailto:dantelugo1505@gmail.com) | Logica |
| gabrieIsosa | [gabrielsosaeest1@gmail.com](mailto:gabrielsosaeest1@gmail.com) | Logica JavaScript |
| LautiCabrera | [lau.cabrera114@gmail.com](mailto:lau.cabrera114@gmail.com) | Contact |
| diego-s10 | [dsena3472@gmail.com](mailto:dsena3472@gmail.com)|
| FedericoZapata | [federico11zapata@gmail.com](mailto:federico11zapata@gmail.com) | Logica Backend |
| barbara1000 | [barbaranunez325@gmail.com](mailto:barbaranunez325@gmail.com)| Formulario|
| julieta-mores-t | [julieta.mores.t@gmail.com](mailto:julieta.mores.t@gmail.com) | Navbar |
| LeiFraz | [Flajarkin99@hotmail.com](Flajarkin99@hotmail.com) | Logica Backend |
| Diana2754 | [dianacc.alali@gmail.com](mailto:dianacc.alali@gmail.com) | 
| AgustinNazaretto | [agustin_nazaretto@hotmail.com](mailto:agustin_nazaretto@hotmail.com)| Footer|
| klicera | [karenlicera@gmail.com](mailto:karenlicera@gmail.com) | Formulario de Contacto |
| SusanoJuicio | [ivanacu2001@gmail.com](mailto:ivanacu2001@gmail.com) | Existencia |
| Ax-966 | [argaxelagustin@gmail.com](mailto:argaxelagustin@gmail.com) | Navegacion |
| salinassm | [salinas.milagros.ayelen@gmail.com](mailto:salinas.milagros.ayelen@gmail.com) | Header |
