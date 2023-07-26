# Guia de uso de `<comandos>` GitHub

## En esta Guia se hará mensión de los comandos utilizados para el control de versiones con GitHub

### Como primer punto es necesario tener instalado github bash

* Link de descarga [git bash](https://git-scm.com/downloads)

Una vez instalado git bash deberás configurar la terminal con tus credenciales siguiendo los siguientes puntos.

El primer paso es configurar el nombre de usuario de tu cuenta de *github*

```console
    $   git config --global user.name "YourNameUser"
```

Ahora deberás configurar el correo de tu cuenta de *github*

```console
    $   git config --global user.email youremail@mail.com
```

Configura de manera predeterminada el editor `nano` para nombrar los **commit's**

```console
    $   git config --global core.editor "nano"
```

Configuración de administrador de creenciales de Windows para Git

```console
    $   git config --global credential.helper wincred
```

Para ver la configuración que hemos hecho debería usar el comando:

```console
    $   git config --list
```

### Comandos básicos

> para ver más opciones del comando utiliza **_--help_**


* `git init` : _Inicializa un repositorio Git en un directorio vacío o en un directorio existente._
  * ejm: "ejecuta este comando dentro del proyecto para inicializar"
    ```console
        $ git init
    ```
* `git clone` : _Clona un repositorio Git en un nuevo directorio._
    * ejm: "ejecuta este comando para clonar un repositorio"
    ```console
        $ git clone https://github.com/yourrepository.git
    ```
* `git add` : _Agrega cambios al área de preparación para ser confirmados en el próximo commit._
    * ejm:  
    ```console
        $ git add archivo.txt // agregar solo un archivo especificando el nombre
            ó 
        $ git add . // para agregar todos los archivos
    ```
* `git commit` : _Toma una instantánea del estado actual del proyecto y la guarda en el historial de Git._
    * ejm:
    ```console
        $   git commit -m "Agregado archivo.txt"
    ```

* `git status` : _Muestra el estado actual del directorio de trabajo y el área de preparación._
    * ejm: "este comando mostrara en lista los chambios que se han echo en el directorio
    ```console
        $   git status
    ```
* `git log` : _Muestra el historial de confirmaciones en orden cronológico inverso._
    * ejm:
    ```console
        $   git log
    ```
* `git diff` : _Muestra las diferencias entre los archivos en el directorio de trabajo y el área de preparación._
    * ejm:
    ```console
        $   git diff
    ```
* `git push` : _Envía los cambios confirmados en la rama actual al repositorio remoto._
    * ejm:
    ```console
        $   git push -u origin master
    ```
* `git pull` : _Recupera los cambios del repositorio remoto y los fusiona con la rama actual._
    * ejm:
    ```console
        $   git pull
    ```
* `git branch` : _Lista, crea o elimina ramas._
    * ejm:
    ```console
        $   git branch 
    ```
* `git checkout` : _Cambia a una rama o restaura archivos del historial de Git._
    * ejm:
    ```console
        $   git checkout develop
    ```
* `git merge` : _Fusiona cambios de otra rama en la rama actual._
    * ejm:
    ```console
        $   git merge
    ```
* `git reset` : _Deshace cambios confirmados y los elimina del historial de Git._
    * ejm:
    ```console
        $   git reset
    ```
* `git stash` : _Guarda temporalmente los cambios que aún no están listos para ser confirmados._

## Nombrar commit´s

<body>
    <p>
        Nombrar los commits de manera profesional es importante para 
        mantener un historial de cambios claroo y fácil de mantener
    </p>
    <p>
        Cada una de las etiquetas tiene un significado específico y ayuda a describir claramente el tipo de cambio que se está realizando en el código fuente. Aquí está una breve descripción de cada una de las etiquetas:
    </p>
 </body>

* ``feat`` : _para una nueva característica o funcionalidad añadida._
* ``fix`` : _para un error o problema corregido._
* ``build`` : _para cambios relacionados con la construcción o configuración del proyecto._
* ``chore`` : _para cambios que no afectan al código fuente, como actualizar dependencias o tareas de mantenimiento._
* ``ci`` : _para cambios en la configuración del sistema de integración continua._
* ``docs`` : _para cambios en la documentación del proyecto._
* ``perf`` : _para mejoras de rendimiento._
* ``refactor`` : _para cambios que no agregan nuevas funcionalidades ni corrigen errores, pero mejoran la calidad del código._
* ``style`` : _para cambios en la apariencia del código fuente, como el formato o la sintaxis._
* ``test`` : _para cambios relacionados con pruebas o casos de prueba._

Ejemplo:

El usuario “user01” esta haciendo cambios en el archivo1.txt

* Paso 1:
Cuando este usuario termine de realizar la funcionalidad este deberá usar un etiqueta como “feat” y seguir lo siguientes pasos:
```console
git add archivo.txt
```
Agregar el “archivo.txt” a la preparación. para subir cambios


* Paso 2:
Este comando abrirá el editor configurado por nano, aquí podrás redactar el commit

```console
git commit
```

En este caso, se utiliza la etiqueta "feat" para indicar que se ha agregado una nueva funcionalidad. en este caso en la sección de "products", seguido del cambio especificado agregando las acciones realizadas como la siguiente nota.

> feat(products): add search functions in the products module -This commit adds a new function to the search bar-This will improve the overall user experience and make it easier to find relevant information. Para guardar los cambios del editor nano, deberás usar Ctrl + o y Ctrl + x para salir del editor Agrega un commit mas corto se puede hacer de la siguiente manera: 

```console
git commit -m "fix(products): add search functions in the products module"
```
Agregar una descripcion más detallada si es necesario desde el editor. Recuerda que configuraste el edito nano, para agregar una descripción mas detallada.


* Paso 3:
Enviar los cambios al servidor Github.

`Importante descargar cambios de la rama origin`

```console
// descargar cambios de una rama
git pull
// ó
git pull origin master
```
> (master) es una variante de las ramas existentes en el desarrollo Pueden existir más de una, en un solo proyecto.

__Enviar los cambios__
```console
git push -u origin master
```
Si te salta algún error, es importante tomar medidas, que apliquen dependiendo el error.
