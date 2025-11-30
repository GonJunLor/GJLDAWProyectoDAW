<div style="position: sticky; top: 0; left: 0; width: 100%; background-color: rgba(255, 255, 255, 1); padding: 10px; border-bottom: 1px solid #ccc; z-index: 999;">
    <a href="README.md">Inicio</a> |<>|
    <a href="ServidorDesarrollo.md">Servidor de desarrollo</a> |<>|
    <a href="ClienteDesarrollo.md">Cliente de desarrollo</a> |<>|
    <a href="GitHub.md">GitHub</a>
</div>
<hr>

<!-- title: README -->
# ENTORNO DE EXPLOTACIÓN

|  CFGS DESARROLLO  DE APLICACIONES WEB |
|:-----------:|
|![Alt](webroot/media/images/portada.jpg)|
| DESPLIEGUE DE APLICACIONES WEB
| CYBERSEGURIDAD
| DAWES Tema 2. INSTALACIÓN, CONFIGURACIÓN Y DOCUMENTACIÓN DE ENTORNO DE DESARROLLO Y DEL ENTORNO DE EXPLOTACIÓN |


- [ENTORNO DE EXPLOTACIÓN](#entorno-de-explotación)
  - [**Conexión por sftp y ssh**](#conexión-por-sftp-y-ssh)
  - [**Crear un subdominio**](#crear-un-subdominio)
  - [**Publicar desde GitHub**](#publicar-desde-github)
  - [**Subir versión estable en github**](#subir-versión-estable-en-github)
  - [**Bases de datos**](#bases-de-datos)
  - [**Archivo de configuracion de conexión a BBDD**](#archivo-de-configuracion-de-conexión-a-bbdd)
  - [**Fichero .htaccess**](#fichero-htaccess)
  - [**DNS**](#dns)


## <h2>**Conexión por sftp y ssh**</h2>

**<h3>SFTP</h3>**
Lo primero es tener los datos de conexión, por si no los tenemos vamos a *sitios web y dominios*, damos a *ftp* y en nuestro nombre  se abre una ventana donde podemos configurar el nombre de usuario y contraseña, además de ver que el acceso SSH es */bin/bash* y ver también nuestra ip.

Para conectarnos lo hacemos con [mobaXterm](ClienteDesarrollo.md#3-mobaxterm) igual que cuando nos conectamos a nuestro servidor solo que con los datos que hemos configurado.

**<h3>SSH</h3>**
Tenemos dos opciones, la primera es directamente desde plesk en *sitios web y dominios*, damos a *SSH Terminal*, se nos abre la consola de comando donde poder hacer lo que tengamos permisos.

La segunda opción es con un cliente como [mobaXterm](ClienteDesarrollo.md#3-mobaxterm) igual que cuando nos conectamos a nuestro servidor pero con los mismos datos de sftp.


## <h2>**Crear un subdominio**</h2>
Desde plesk en *sitios web y dominios* damos a *añadir subdominio*.

Se abre una ventana donde ponemos el nombre del subdominio, normalmente el del proyecto que queremos subir. Elegimos también un directorio para guadar dicho proyecto, en nuestro caso será el mismo que ya tenemos dentro de httpdocs. Muy importante asegurarse de que le nombre de la carpeta sea solo el del proyecto, ya que por defecto plesk pone el dominio entero a esta carpeta, por lo que tenemos que borrarlo antes de darle aceptar.


## <h2>**Publicar desde GitHub**</h2>
Lo primero es tener abierto nuestro repositorio en github porque vamos a copiar y configurar cosas.

En plesk vamos a sitios web y dominios, entramos nuestro dominio principal y damos al icono de git.

En github copiamos la url de ssh.

En plesk añadimos repositorio, al pegar la url de github nos sale una sección para crear clave ssh pública, tenemos que crear una para cada repositorio, copiamos esa clave y vamos a github a las opciones de nuestro repostorio a deply keys. Una vez aquí añadimos una nueva clave pegando la que hemos copiado de plesk, poniendo un nombre significativo y dejando *Allow write access* desmarcado.

Volvemos a plesk, modificamos el nombre del repositorio como queramos, nos aseguramos que el modo despliegue esta en automático. En ruta de acceso elegimos la carpeta de nuestro proyecto (si no la tenemos la creamos pero es recomendable que esté vacia) dentro de httpdocs. 

Ya podemos dar a crear, esto clonará el repositorio de github a plesk.

Si no ha habido errores volvemos a git en plesk y damos a configuración del repositorio en la tarjeta de nuestro proyecto (icono del medio abajo a la derecha). Al abrir vemos que hay un nuevo enlace, el url de webhook, el cual copiamos y vamos a github.

En github entramos en settings/webhooks y damos a añadir webhook. Pegamos el url pero le añadimos plesk. al principio del dominio, elegimos application/json en content type, nos aseguramos que está marcada la opcion *Just the push event* y damos a añadir.

Con todo esto cada vez que hagamos push a la rama principal se subirá automáticamente a plesk.

## <h2>**Subir versión estable en github**</h2>
Descargamos el proyecto comprimido en zip desde la sección de releases de github que previamente vamos haciendo con versiones estables de nuestro proyecto.

Lo descomprimimos en nuestro pc y lo subimos al servidor por ftp, si es necesario borramos o modificamos archivos de configuración o lo que sea antes de subirlo.

## <h2>**Bases de datos**</h2>

Para trabajar con bases de datos lo hacemos en dos pasos, el primero será desde plesk donde crearemos la BBDD asociada a un dominio o proyecto y también crearemos el usuario para gestionarla. El segundo será desde phpMyAdmin donde ejecutaremos codigos sql para crear tablas, hacer carga inicial y borrarlas.

**<h3>En plesk</h3>**
En *sitios web y dominios* damos a *Bases de datos* y *añadir base de datos*.

En la ventana que se abre elegimos el nombre de la BBDD, el sitio relacionado (este será un subdominio asociado a un proyecto que tenemos previamnete creado) y creamos un usuario con su contraseña.

Una vez que le damos a crear ya nos aparece la opcion de abrir phpMyAdmin.

**<h3>En phpMyAdmin</h3>**
Aqui gestionamos únicamente la bbdd que creamos antes, no podemos ver todas las que hay en plesk. 

Nos vamos a la pestaña SQL, copiamos o escribimos el código a ejecutar y antes de darle a continuar en la parte de abajo Guardamos esta consulta en favoritos poniéndole un nombre. 

Al hacer ésto aparece una nueva sección abajo *Consulta guardada en favoritos* donde tenemos una lista desplegable con todas las que guardemos para poder seleccionarla en cualquier momento y darla a continuar abajo a la derecha para volver a ejecutarla.

## <h2>**Archivo de configuracion de conexión a BBDD**</h2>
Lo primero es crear unas variables de entorno con los datos de la conexión en el archivo .htaccess del proyecto donde sea necesario.
````Bash
SetEnv DB_DSN "mysql:host=localhost; dbname=DBGJLDWESProyectoTema4"
SetEnv DB_USERNAME "userGJLDWESProyectoTema4"
SetEnv DB_PASSWORD "5813Libro-Puro"
````

Este es el contenido del archivo de configuración en explotación.
````Bash
<?php
// Lee las variables de entorno para DSN, USERNAME y PASSWORD
define('DSN', getenv('DB_DSN'));
define('USERNAME', getenv('DB_USERNAME'));
define('PASSWORD', getenv('DB_PASSWORD'));

// Verificar si las variables se cargaron correctamente (opcional pero recomendado)
if (!DSN || !USERNAME || !PASSWORD) {
    // Aquí puedes lanzar una excepción o registrar un error si faltan las credenciales
    error_log("ERROR: Las variables de entorno de la base de datos no están definidas.");
}
?>
````

El objetivo con todo esto es que el archivo de configuración en explotación (rama master) no tenga la contraseñas, usuarios ni datos de la bbdd, a diferencia del entorno de explotación (rama developerGJL) que sí los tiene. Como el resto del código php es el mismo en los dos entornos, usa el mismo archivo (confDBPDO.php). 

Antes de empezar guarda una copia de seguridad por si hay que volver a restaurar los archivos.

Lo primero es añadirlo al archivo .gitignore (lo hacemos todo desde developerGJL y luego ya fusionamos con master).
````Bash
conf/confDBPDO.php
```` 
Después lo borramos del seguimiento de git (si quieremos asegurarnos más podemos borrarlo por completo sin usar --cached y luego volver a crearlo al final).
````Bash
git rm --cached conf/confDBPDO.php
```` 

En este punto ya no debería estar el archivo en github en ninguna rama, ahora tenemos que crearlo o modificarlo con los datos de conexión del entorno de desarrollo y hacer otra versión para subirla manualmente al entorno de explotación.

## <h2>**Fichero .htaccess**</h2>
https://www.ionos.es/digitalguide/hosting/cuestiones-tecnicas/los-mejores-trucos-para-archivos-htaccess/
````Bash
# Redirección a indice personalizado
directoryindex indexProyectoCIB.php

# Para que funcione el metodo head('WWW-Authenticate: Basic realm="Contenido restringido"') en php
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
</IfModule>

# Redirección de errores a paginas personalizadas en carpeta error de raiz del dominio/subdominio
ErrorDocument 404 /error/404.html
ErrorDocument 403 /error/403.html
ErrorDocument 500 /error/500.html

# Redirección http a https (cambiar ip de https)
RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://10.199.8.153/$1 [R,L]

# Variables de entorno para BBDD
SetEnv DB_DSN "mysql:host=localhost; dbname=DBGJLDWESProyectoTema4"
SetEnv DB_USERNAME "userGJLDWESProyectoTema4"
SetEnv DB_PASSWORD "5813Libro-Puro"
````

## <h2>**DNS**</h2>


> **Gonzalo Junquera Lorenzo**  
> Curso: 2025/2026  
> 2º Curso CFGS Desarrollo de Aplicaciones Web  

