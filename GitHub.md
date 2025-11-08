<!-- title: README -->
# GIT Y GITHUB

|  CFGS DESARROLLO  DE APLICACIONES WEB |
|:-----------:|
|![Alt](webroot/media/images/portada.jpg)|
| DESPLIEGUE DE APLICACIONES WEB
| CYBERSEGURIDAD
| DAWES Tema 2. INSTALACIÓN, CONFIGURACIÓN Y DOCUMENTACIÓN DE ENTORNO DE DESARROLLO Y DEL ENTORNO DE EXPLOTACIÓN |


- [GIT Y GITHUB](#git-y-github)
  - [Git](#git)
    - [**Instalación**](#instalación)
    - [**Configuracion global en local**](#configuracion-global-en-local)
    - [**Remover archivo del seguimiento de git.**](#remover-archivo-del-seguimiento-de-git)
  - [GitHub](#github)


## <h1>Git</h1>

### <h2>**Instalación**</h2>
https://git-scm.com/

Lo descargamos desde la web oficial. 

Lo ejecutamos y vamos dando a *next*, en una ventana pregunta por el editor por defecto, yo he escogido *Use NotePad as Git's default editor* el resto de ventanas todo *next* hasta llegar a *Install* y ya estaría instalado.

### <h2>**Configuracion global en local**</h2>

Abrimos git bash y configuramos nuestro email y nuestro nombre
````Bash
git config --global user.name "Tu Nombre Completo"
git config --global user.email "tu.email@ejemplo.com"
````

### <h2>**Remover archivo del seguimiento de git.**</h2> 

git rm elimina un archivo tanto del directorio de trabajo como del área de preparación de Git, marcando su eliminación para el próximo commit. Este comando combina la eliminación del archivo con git add para que los cambios se preparen y se registren en el historial. Para solo eliminar un archivo del seguimiento de Git sin borrarlo del disco, se puede usar la opción --cached. 
Uso básico 
• git rm <nombre_archivo>: Elimina un archivo de tu proyecto y lo marca para ser eliminado en el siguiente commit.
• git rm <archivo1> <archivo2>: Elimina varios archivos a la vez.
• git rm -r <nombre_directorio>: Elimina un directorio completo y todo su contenido. 
Opciones útiles 
• --cached: Elimina el archivo del índice (área de preparación) pero lo conserva en tu directorio de trabajo. Esto hace que Git deje de rastrear el archivo, pero sigue estando en tu disco.
• --force o -f: Fuerza la eliminación incluso si hay cambios no guardados en el archivo. Se usa con precaución para evitar la pérdida de datos.

## <h1>GitHub</h1>



> **Gonzalo Junquera Lorenzo**  
> Curso: 2025/2026  
> 2º Curso CFGS Desarrollo de Aplicaciones Web  

