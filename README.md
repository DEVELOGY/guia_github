# Guia de uso de `<comandos>` GitHub

## En esta Guia se hará mensión de los comandos utilizados para el control de versiones con GitHub

### Configuraciones básicas de github:
> Instalación de git bash (windows)

Link de descarga [git bash](https://git-scm.com/downloads)

> Instalación de git bash en (Linux,Mac)
Obtener la última versión de lanzamiento disponible (Debian/Ubuntu).

```bash
sudo apt-get install git
```

Para Ubuntu:
```bash
sudo add-apt-repository ppa:git-core/ppa 

sudo apt update; apt install git
```

### Una vez instalado git bash deberás configurar la terminal con tus credenciales siguiendo las instrucciones.

Abre una terinal de git bash. 
El primer paso es configurar el nombre de usuario de tu cuenta de *github*

```console
git config --global user.name "YourNameUser"
```

Ahora deberás configurar el correo de tu cuenta de *github*

```console
git config --global user.email youremail@mail.com
```

Configura de manera predeterminada el editor `nano` para nombrar los **commit's**

```console
git config --global core.editor "nano"
```

Configuración de administrador de creenciales para Git

```console
git config --global credential.helper wincred
```

Para ver la configuración que hemos hecho debería usar el comando:

```console
git config --list
```

### Comandos básicos

> para ver más opciones del comando utiliza **_--help_**
<table>
    <thead>
        <tr>
            <th>Comando</th>
            <th>Descripción</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>git init</td>
            <td>
                Inicializa un repositorio git en el directorio actual. <br>
                Ejm: Ejecuta este comando dentro del proyecto para inicializar tu área de trabajo: 
                <br>
                <br>
                <code>user/local/myrepository$ git init</code>
            </td>
        </tr>
        <tr>
            <td>git clone</td>
            <td>
                Clona un repositorio Git en un nuevo directorio. <br>
                Ejm: Ejecuta este comando para clonar un repositorio: 
                <br>
                <br>
                <code>git clone https://github.com/yourrepository.git</code>
            </td>
        </tr>
        <tr>
            <td>git add </td>
            <td>
                Agrega cambios al área de preparación para ser confirmados en el próximo commit 
                <br>
                <br>
                <code>git add archivo.txt // agregar solo un archivo especificando el nombre</code><br>
                <code>git add . // para agregar todos los archivos con cambios</code>
            </td>
        </tr>
        <tr>
            <td>git commit</td>
            <td>
                Toma una instantánea del estado actual del proyecto y la guarda en el historial de Git.
                <br>
                <br>
                <code>git commit -m "Agregado archivo.txt"</code>
            </td>
        </tr>
        <tr>
            <td>git status</td>
            <td>
                Muestra el estado actual del árbol de trabajo. <br>
                Ejm: este comando mostrara en lista los chambios que se han echo en el directorio.
                <br>
                <br>
                <code>git status</code>
            </td>
        </tr>
        <tr>
            <td>git log</td>
            <td>
                Muestra el historial de confirmaciones en orden cronológico inverso.
                <br>
                <br>
                <code>git log</code>
            </td>
        </tr>
        <tr>
            <td>git diff</td>
            <td>
                Muestra las diferencias entre los archivos en el directorio de trabajo y el área de preparación.
                <br>
                <br>
                <code>git diff namefile.txt</code>
            </td>
        </tr>
        <tr>
            <td>git push</td>
            <td>
                Envía los cambios confirmados en la rama actual al repositorio remoto
                <br>
                <br>
                <code>git push origin master //nombre de la rama en la cual estas trabajando</code>
            </td>
        </tr>
        <tr>
            <td>git pull</td>
            <td>
                Recupera los cambios del repositorio remoto y los fusiona con la rama actual
                <br>
                Ejm: Se pueden utilizar variantes dependiendo el caso.
                <br> 
                <code>git pull // recupera los cambios de las rama remoto actual</code><br>
                <code>git pull origin master //recupera cambios de una rama 'master'</code><br>
            </td>
        </tr>
        <tr>
            <td>git branch</td>
            <td>
                Lista, crea o elimina ramas del área de trabajo
                <br>
                <br>
                <code>git  branch //muestra todas las ramas locales</code><br>
                <code>git  branch develop //crea una rama con el nombre 'develop'</code><br>
                <code>git branch -d develop // elimina la rama 'develop</code><br>
                <code>git checkout -b develop // crea una rama 'develop' y cambia el area de trabajo a la nueva rama</code>
            </td>
        </tr>
        <tr>
            <td>git checkout</td>
            <td>
                Cambia a una rama o restaura archivos del historial de git <br><br>
                <code>git checkout master //cambiarse a la rama 'master'</code><br>
                <code>git checkout HEAD^ -- file.txt //restaurar un archivo a su estado anterior</code><br>
            </td>
        </tr>
        <tr>
            <td>git merge</td>
            <td>
                Fusiona cambios de otra rama en la rama actual <br><br>
                Ejm: Actualmente estoy trabajando en 'develop', al terminar cambios realiza un 'commit' y continua con lo siguiente: <br>
                <code>git commit -m "feat(app):cambios file.txt rama -> develop"</code> <br>
                <code>git checkout master // cambio a la rama 'master' para hacer `merge` develop->master</code><br>
                <code>git merge develop</code>
            </td>
        </tr>
        <tr>
            <td>git stash</td>
            <td>
                Guarda temporalmente los cambios que aún no estan listos para ser confirmados <br><br>
                <code>git stash // guarda los cambios de manera local, puedes hacer un `git pull` para comprobar si existen cambios en la misma rama de trabajo</code><br>
                <code>git stash pop //recupera los cambios guardados de manera local</code>
            </td>
        </tr>
    </tbody>
</table>

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

### Ejemplo:

El usuario “user01” esta haciendo cambios en el archivo.txt

* Paso 1:
Cuando este usuario termine de realizar la funcionalidad, este deberá usar un etiqueta como “feat” y seguir lo siguientes pasos:

 > Agregar el “archivo.txt” a la preparación. para subir cambios
```console
git add archivo.txt
```


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
Agregar una descripcion más detallada si es necesario desde el editor. Recuerda que configuraste el editor nano, para agregar una descripción mas detallada.


* Paso 3:
Enviar los cambios al servidor Github.

`Importante descargar cambios de la rama origin, evita conflictos al momento de hacer push`

```console
# descargar cambios de rama origin
git pull
# ó
git pull origin master
```
> (master) es una variante de las ramas existentes en el desarrollo Pueden existir más de una, en un solo proyecto.

__Enviar los cambios__
```console
git push -u origin master
```
Si te salta algún error, es importante tomar medidas, que apliquen dependiendo el error.
