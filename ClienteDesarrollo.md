<!-- title: README -->
# CLIENTE DE DESARROLLO - WINDOWS 10/11

|  CFGS DESARROLLO  DE APLICACIONES WEB |
|:-----------:|
|![Alt](webroot/media/images/portada.jpg)|
| DESPLIEGUE DE APLICACIONES WEB
| CYBERSEGURIDAD
| DAWES Tema 2. INSTALACIÓN, CONFIGURACIÓN Y DOCUMENTACIÓN DE ENTORNO DE DESARROLLO Y DEL ENTORNO DE EXPLOTACIÓN |


- [CLIENTE DE DESARROLLO - WINDOWS 10/11](#cliente-de-desarrollo---windows-1011)
  - [**1 Configuración inicial**](#1-configuración-inicial)
    - [*Nombre y configuración de red*](#nombre-y-configuración-de-red)
    - [*Cuentas administradoras*](#cuentas-administradoras)
  - [**2 Navegadores**](#2-navegadores)
  - [**3 MobaXterm**](#3-mobaxterm)
    - [*Instalación*](#instalación)
    - [*Configuración*](#configuración)
    - [*Ejemplo de uso*](#ejemplo-de-uso)
  - [**4 Netbeans**](#4-netbeans)
    - [*Instalación*](#instalación-1)
    - [*Configuración*](#configuración-1)
    - [*Ejemplo de uso*](#ejemplo-de-uso-1)
  - [**5 Visual Studio Code**](#5-visual-studio-code)
    - [*Instalación*](#instalación-2)
    - [*Configuración*](#configuración-2)
    - [*Ejemplo de uso*](#ejemplo-de-uso-2)
      - [**Abrir proyecto**](#abrir-proyecto)
      - [**Depurar con Xdebug**](#depurar-con-xdebug)
      - [**Conexión SFTP al servidor**](#conexión-sftp-al-servidor)
      - [**Conectar a base de datos**](#conectar-a-base-de-datos)


## <h2>**1 Configuración inicial**</h2>

### <h2>*Nombre y configuración de red*</h2>

### <h2>*Cuentas administradoras*</h2>

## <h2>**2 Navegadores**</h2>

## <h2>**3 MobaXterm**</h2>
- ver la parte del servidor y local con el otro programa

### <h2>*Instalación*</h2>

### <h2>*Configuración*</h2>

### <h2>*Ejemplo de uso*</h2>

## <h2>**4 Netbeans**</h2>

### <h2>*Instalación*</h2>
Apache NetBeans IDE 20

### <h2>*Configuración*</h2>
- configurar carpetas por defecto, cambiar las rutas

### <h2>*Ejemplo de uso*</h2>
- version y plugins de netbeans (las que esten por defecto, donde se ve)
- como usar github
- como llevar a casa y volver a usar aquí (es github)
- capturas solo de la parte ineteresada, no de toda la pantalla

**<h3>Crear proyecto con conexion (SFTP) al servidor</h3>**
- Nuevo proyecto PHP marcando la opción "PHP Application from Remote Server"

![Alt](webroot/media/images/nb1.png)
- Ponemos nombre de proyecto y cambiamos la ruta por la nuestra personal

![Alt](webroot/media/images/nb2.png)
- Configuramos la url con nuestro servidor y el nombre del proyecto en el servidor, en el caso del proyecto principal no tiene carpeta es la raíz (/)

![Alt](webroot/media/images/nb3.png)
- La primera vez que creamos un proyecto con conexión al servidor hay que configurarlo con nombre de usuario, contraseña y directorio inicial

![Alt](webroot/media/images/nb4.png)
- Si todo ha ido bien se conectará al servidor y entrará en la carpeta del proyecto que previamente tenemos que haber creado y que haya por lo menos un archivo en ella. Aquí ya marcamos para que se bajen los archivos que queramos.

![Alt](webroot/media/images/nb5.png)

**<h3>Borrar proyecto con conexion (SFTP) al servidor</h3>**
- botón secundario sobre el proyecto y delete. Nos pedirá confirmación y si queremos que borre los archivos en nuestro ordenador. Los del servidor lo tenemos que borrar a mano.

![Alt](webroot/media/images/nb6.png)


## <h2>**5 Visual Studio Code**</h2>

### <h2>*Instalación*</h2>

### <h2>*Configuración*</h2>

**<h3>Git Graph (Extensión)</h3>**

<img src="webroot/media/images/vscExt01.png" width="600px">

**<h3>Live Server (Extensión)</h3>**

<img src="webroot/media/images/vscExt02.png" width="600px">

**<h3>Markdown All in One (Extensión)</h3>**

<img src="webroot/media/images/vscExt03.png" width="600px">

**<h3>SQLTools (Extensión)</h3>**

<img src="webroot/media/images/vscExt04.png" width="600px">

**<h3>SQLTools MySQL/MariaDB/TiDB (Extensión)</h3>**

<img src="webroot/media/images/vscExt05.png" width="600px">

**<h3>vscode-pdf (Extensión)</h3>**

<img src="webroot/media/images/vscExt06.png" width="600px">

**<h3>SFTP (Extensión)</h3>**

<img src="webroot/media/images/vscExt07.png" width="600px">

**<h3>PHP Intelephense (Extensión)</h3>**

<img src="webroot/media/images/vscExt08.png" width="600px">

Para que funcione hay deshabilitar la que viene por defecto, buscamos @builtin php en el buscador de extensiones y la desactivamos.

<img src="webroot/media/images/vscExt09.png" width="600px">

**<h3>Conventional Commits (Extensión)</h3>**

<img src="webroot/media/images/vscExt10.png" width="600px">

**<h3>Auto Close Tag (Extensión)</h3>**

<img src="webroot/media/images/vscExt11.png" width="600px">

**<h3>PHP Extension Pack (Extensión)</h3>**
https://marketplace.visualstudio.com/items?itemName=xdebug.php-pack&ssr=false#overview

<img src="webroot/media/images/vscExt12.png" width="600px">
Esta extensión instala otras dos, la PHP IntelliSense

https://marketplace.visualstudio.com/items?itemName=zobo.php-intellisense

y PHP Debug

https://marketplace.visualstudio.com/items?itemName=xdebug.php-debug

### <h2>*Ejemplo de uso*</h2>

#### **<h3>Abrir proyecto</h3>**

#### **<h3>Depurar con Xdebug</h3>**
Para poder depurar necesitamos tener instalada la extensión [PHP Extension Pack](https://marketplace.visualstudio.com/items?itemName=xdebug.php-pack&ssr=false#overview) la cual instala la extensión PHP Debug que necesitamos.

Le damos a la pestaña de depuración  <img src="webroot/media/images/vscXdebug01.png" width="30px"> y damos en "*create a launch.json file*", esto creara un archivo de configuración (launch.json) en la carpeta .vscode.

Abrimos el archivo launch.json y añadimos la ruta de nuestro proyecto en "pathMappings". 

````Bash
{
    "name": "Listen for Xdebug",
    "type": "php",
    "request": "launch",
    "port": 9003,
    "pathMappings": {
        "/var/www/html/GJLDWESProyectoTema4": "${workspaceRoot}"
    }
},
````
>Es importante saber que para que funcione esta forma de hacerlo tenemos que abrir solo nuestro proyecto GJLDWESProyectoTema4 en una ventana de visual studio code, no añadir varios proyectos a un Workspace. Si necesitamos abrir varios proyectos a la vez podemos abrir todas las ventanas que queramos de File>New Window.

Para empezar a depurar tenemos que añadir un punto de parada al lado de la linea de código dónde queramos que pause la ejecución, se hace poniendo un punto rojo a la izquierda del número de línea.

Vamos a la pestaña de depuración, en el desplegable ponemos listen for Xdebug y le damos al play verde. Vamos al navegador, abrimos la página para que cargue y empiece a depurar (en el navegador se quedara cargando y si tardamos mucho puede que salga un error de TimeOut)

<img src="webroot/media/images/vscXdebug02.png" width="400px">

En variables nos saldrán todas las variables locales que se hayan cargado antes del punto de parada que pusimos y tambien podemos ver las Superglobales y las constantes. 

Aparecerá una barra con botones para controlar la ejecución de la depuración

<img src="webroot/media/images/vscXdebug03.png" width="250px">

En el codigo resaltará en amarillo por donde va la ejecución del codigo, en esta prueba esta en el punto que había puesto al principio.

<img src="webroot/media/images/vscXdebug04.png" width="400px">

Para finalizar ejecutamos hasta que acabe el codigo o le damos al cuadrado rojo en la barra de botones.


#### **<h3>Conexión SFTP al servidor</h3>**

#### **<h3>Conectar a base de datos</h3>**


> **Gonzalo Junquera Lorenzo**  
> Curso: 2025/2026  
> 2º Curso CFGS Desarrollo de Aplicaciones Web  

