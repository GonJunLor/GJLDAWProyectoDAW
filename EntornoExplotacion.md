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

## <h2>**Publicar desde GitHub**</h2>
Lo primero es tener abierto nuestro repositorio en github porque vamos a copiar y configurar cosas.

En plesk vamos a sitios web y dominios, entramos nuestro dominio principal y damos al icono de git.

En github copiamos la url de ssh.

En plesk añadimos repositorio, al pegar la url de github nos sale una clave ssh pública, copiamos esa clave y vamos a github a las opciones de nuestro repostorio a deply keys. Una vez aquí añadimos una nueva clave pegando la que hemos copiado de plesk, poniendo un nombre significativo y dejando *Allow write access* desmarcado.

Volvemos a plesk, modificamos el nombre del repositorio como queramos, nos aseguramos que el modo despliegue esta en automático. En ruta de acceso elegimos la carpeta de nuestro proyecto (si no la tenemos la creamos pero es recomendable que esté vacia) dentro de httpdocs. 

Ya podemos dar a crear, esto clonará el repositorio de github a plesk.

Si no ha habido errores volvemos a git en plesk y damos a configuración del repositorio en la tarjeta de nuestro proyecto (icono del medio abajo a la derecha). Al abrir vemos que hay un nuevo enlace, el url de webhook, el cual copiamos y vamos a github.

En github entramos en settings/webhooks y damos a añadir webhook. Pegamos el url pero le añadimos plesk. al principio del dominio, elegimos application/json en content type, nos aseguramos que está marcada la opcion *Just the push event* y damos a añadir.

Con todo esto cada vez que hagamos push a la rama principal se subirá automáticamente a plesk.

1.- Crear un subdominio
nombreproyecto
alojamiento /httpdocs/nombreproyecto

Subir versión estable en github
Opcion1: .zip descargando una version, descomprimiendo y subiendo por ftp
Opcion2: sincronizar con github y rama master para que suba automáticamente

3.- Conexión por ftp
Como configurar usuario y contraseña en plesk para poder conectarnos despues por ftp
subir por ftp cosas con mobaXterm y con filezilla.

4.- BBDD 
  - Como crear la bbdd y usuario
  - como hacer creacion tablas, craga inicial y borrado desde phpmyadmin y SQL con las consultas almacenadas

5.- head()
contenido archivo htaccess para poder usar header('WWW-Authenticate: Basic realm="Contenido restringido"');
header('HTTP/1.0 401 Unauthorized');



> **Gonzalo Junquera Lorenzo**  
> Curso: 2025/2026  
> 2º Curso CFGS Desarrollo de Aplicaciones Web  

