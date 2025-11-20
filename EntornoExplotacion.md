<!-- title: README -->
# ENTORNO DE EXPLOTACIÓN

|  CFGS DESARROLLO  DE APLICACIONES WEB |
|:-----------:|
|![Alt](webroot/media/images/portada.jpg)|
| DESPLIEGUE DE APLICACIONES WEB
| CYBERSEGURIDAD
| DAWES Tema 2. INSTALACIÓN, CONFIGURACIÓN Y DOCUMENTACIÓN DE ENTORNO DE DESARROLLO Y DEL ENTORNO DE EXPLOTACIÓN |


- [ENTORNO DE EXPLOTACIÓN](#entorno-de-explotación)
  - [**Publicar desde GitHub**](#publicar-desde-github)
  - [**Subir versión estable en github**](#subir-versión-estable-en-github)
  - [**Crear un subdominio**](#crear-un-subdominio)
  - [**Conexión por ftp**](#conexión-por-ftp)
  - [**Bases de datos**](#bases-de-datos)
  - [**Publicar desde GitHub**](#publicar-desde-github-1)

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
.zip descargando una version, descomprimiendo y subiendo por ftp

## <h2>**Crear un subdominio**</h2>
nombreproyecto
alojamiento /httpdocs/nombreproyecto

## <h2>**Conexión por ftp**</h2>
Como configurar usuario y contraseña en plesk para poder conectarnos despues por ftp
subir por ftp cosas con mobaXterm y con filezilla.

## <h2>**Bases de datos**</h2>
  - Como crear la bbdd y usuario
  - como hacer creacion tablas, craga inicial y borrado desde phpmyadmin y SQL con las consultas almacenadas

## <h2>**Publicar desde GitHub**</h2>
Fichero .htaccess
https://www.ionos.es/digitalguide/hosting/cuestiones-tecnicas/los-mejores-trucos-para-archivos-htaccess/
````Bash
# Redirección a indice personalizado
directoryindex indexProyectoCIB.php

# Para que funcione el metodo head('WWW-Authenticate: Basic realm="Contenido restringido"') en php
RewriteEngine On
RewriteCond %{HTTP:Authorization} ^(.*)
RewriteRule .* - [E=HTTP_AUTHORIZATION:%1]

# Redirección de errores a paginas personalizadas en carpeta error de raiz del dominio/subdominio
ErrorDocument 404 /error/404.html
ErrorDocument 403 /error/403.html
ErrorDocument 500 /error/500.html

#Redirección http a https (cambiar ip de https)
RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://10.199.8.153/$1 [R,L]
````

> **Gonzalo Junquera Lorenzo**  
> Curso: 2025/2026  
> 2º Curso CFGS Desarrollo de Aplicaciones Web  

