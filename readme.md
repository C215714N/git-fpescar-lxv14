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

Antes de comenzar a trabajar en un proyecto es importante que configuremos nuestro nombre de usuario y correo con el que seremos identificados en los diferentes proyectos, cabe aclarar que los mismos son independientes a los datos de nuestra cuenta de GitHub, y para ello utilizaremos los siguientes comandos.

```sh
git config --global user.name "username"
git config --global user.email "user@server"
```
### Crear un repositorio

A continuacion debemos inicializar un repositorio en la carpeta donde vayamos a trabajar y agregar un commit al historial de confirmaciones, primero deberemos haber creado algun archivo en la carpeta donde hayamos inicializado el repositorio. No importa si el archivo fue creado en ese momento o existia desde antes, debido a que git registra como creacion la adhicion de dicho elemento, por primera vez, al repositorio.

```sh
git init                    # inicializamos el repositorio
touch .gitignore            # creamos un archivo de exclusiones (UNIX)
echo "*.log" > .gitignore   # agregamos contenido al archivo
git add .gitignore          # realizamos la captura de codigo
git commit                  # confirmamos los cambios realizados
```

### Clonar un Repositorio

En caso que ya contemos con un repositorio remoto podemos descargar el proyecto desde la linea de comandos y trabajar con un clon, que iremos sincronizando a medida que realicemos cambios en el repositorio local. Es importante tener acceso al mismo, incluso si este es un proyecto publico.

```sh
    git clone https://github.com/c215714n/git-fpescar-lxv14 # clona el repositorio en una carpeta homonima
    cd git-fpescar-lxv14 # abrimos la carpeta para trabajar conel repositorio local
```

### Sincronizacion de Cambios

Cuando realizamos un conjunto de cambios en el repositorio local, y se considera que estan listos para ser integrados a la historia remota. Podemos utilizar los siguientes comandos, teniendo en cuenta que debemos descargar cualquier diferencia existente e integrarla a la misma rama que deseamos actualizar remotamente, antes de poder subir algun cambio.

```sh
    git fetch origin main # descarga el historial de cambios remoto
    git diff origin/main  # compara la rama local con la rama remota
    git pull origin main  # integra los cambios remotos (FETCH+MERGE)
    ...                   # resolver cualquier conflicto existente
    git push origin main  # envia los cambios locales a la rama remota
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
    * __git checkout `HEAD~3`__: mueve el puntero hasta 3 commits por detras de la posicion actual
    * __git diff HEAD^__: muestra las diferencias entre el ultimo commit y el ancestro de este
* __BRANCH__: Apuntador dinamico, que siempre apunta al ultimo commit de la linea de tiempo actual.
    * __git branch__: muestra las ramas identificadas en el repositorio actual.
    * __git branch `branchname`__: crea una rama con el nombre especificado en la referencia actual
    * __git branch -d `branch`__: elimina la rama de forma segura, siempre y cuando este integrada.
    * __git branch -D `branch`__: elimina la rama de manera forzada, aunque no haya sido integrada.
    * __git merge `branch`__: genera un commit que combina los cambios de la rama seleccionada y la actual
    * __git rebase `branch`__: reaplica los commits de la rama seleccionada en la rama actual.
* __TAG__: Apuntador estatico, que se corresponde con algun commit en particular y es utilizado para el versionado.
    * __git tag `tag`__: agrega una etiqueta al commit actual
    * __git tag -d `tag`__: elimina una etiqueta del historial de confirmaciones
    * __git tag -l__: muestra las etiquetas existentes
    * __git push --tags__: sube al repositorio remoto las etiquetas creadas localmente
* __STASH__: Apuntador de la zona temporal, ideal cuando necesitamos cambiar de rama y tenemos cambios pendientes.
    * __git stash__: agregar los cambios pendientes a la zona temporal de cambios.
    * __git stash list__: muestra una lista de los cambios almacenados en la pila stash.
    * __git stash apply__: aplica los cambios de la zona temporal al working directory
    * __git stash drop__: elimina de la zona temporal el ultimo commit de referencia
    * __git stash pop__: aplica los cambios al working directory y los quita de la zona temporal

## Registro

Una de las caracteristicas principales que ofrece git, es el acceso al historial de cambios, pero tambien existen el registro resumido, asi como tambien el registro de operaciones. Cabe destacar que esto hace que nuestro repositorio aumente su tamaño, por lo tanto, tambien contamos con una herramienta de limpieza.

* __git log__: muestra el historial de confirmaciones con el autor, la fecha y el mensaje de commit.
* __git shortlog__: muestra el historial resumido ordenado por autor y por commit.
* __git reflog__: muestra el historial de acciones identificado por cabeceras, desde la ultima hasta la primera.
* __git gc__: herramienta de mantenimiento para la limpieza de commit eliminados o con referencias perdidas.

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
| diego-s10 | [dsena3472@gmail.com](mailto:dsena3472@gmail.com)| Logica FrontEnd |
| FedericoZapata | [federico11zapata@gmail.com](mailto:federico11zapata@gmail.com) | Logica Backend |
| barbara1000 | [barbaranunez325@gmail.com](mailto:barbaranunez325@gmail.com)| Formulario|
| julieta-mores-t | [julieta.mores.t@gmail.com](mailto:julieta.mores.t@gmail.com) | Navbar |
| LeiFraz | [Flajarkin99@hotmail.com](mailto:Flajarkin99@hotmail.com) | Logica Backend |
| AgustinNazaretto | [agustin_nazaretto@hotmail.com](mailto:agustin_nazaretto@hotmail.com)| Footer|
| klicera | [karenlicera@gmail.com](mailto:karenlicera@gmail.com) | Formulario de Contacto |
| SusanoJuicio | [ivanacu2001@gmail.com](mailto:ivanacu2001@gmail.com) | Existencia |
| Ax-966 | [argaxelagustin@gmail.com](mailto:argaxelagustin@gmail.com) | Navegacion |
| salinassm | [salinas.milagros.ayelen@gmail.com](mailto:salinas.milagros.ayelen@gmail.com) | Header |
| JulyMoralez | [julimoralezcaviglia@gmail.com](mailto:julimoralezcaviglia@gmail.com) | Formulario |
| TaliaIvonneOjeda1 | [ivonneivonne17@gmail.com](mailto:ivonnetalia17@gmail.com) | cards |
| JulyMoralez | [julimoralezcaviglia@gmail.com](mailto:julimoralezcaviglia@gmail.com) | Formulario |
| antonellapultrone | [antonellapultrone@gmail.com](mailto:antonellapultrone@gmail.com) | Footer |
| alfre4500 | [alfreagor@gmail.com](mailto:alfreagor@gmail.com) | Footer |
| yaelPilarL | [yaelpilarluque@gmail.com](mailto:yaelpilarluque@gmail.com) | Header |
