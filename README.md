# Lección

## Laboratorio 1

```bash
mateo@equipo:~$ touch prueba.txt
mateo@equipo:~$ ls
prueba.txt
```

### Análisis

* El archivo `prueba.txt` fue creado exitosamente con `touch`.
* `ls` muestra el archivo en el directorio actual, confirmando su creación.

## Laboratorio 2

```bash
mateo@equipo:~$ touch archivo1.txt archivo2.txt archivo3.txt
mateo@equipo:~$ ls
archivo1.txt  archivo2.txt  archivo3.txt  prueba.txt
```

### Análisis

* Se crearon los tres archivos en un solo comando con `touch`.
* `ls` confirma la existencia de los archivos en el directorio actual.

## Laboratorio 3

```bash
mateo@equipo:~$ touch prueba.txt
mateo@equipo:~$ ls -l prueba.txt
-rw-r--r-- 1 mateo mateo 0 2025-05-23 18:25 prueba.txt
```

### Análisis

* El comando `touch prueba.txt` actualiza la fecha y hora de modificación del archivo.
* `ls -l` muestra la nueva marca de tiempo reflejada en el archivo.

## Laboratorio 4

```bash
mateo@equipo:~$ mkdir documentos
mateo@equipo:~$ ls
archivo1.txt  archivo2.txt  archivo3.txt  documentos  prueba.txt
```

### Análisis

* El comando `mkdir documentos` crea un nuevo directorio llamado `documentos`.
* `ls` confirma que el directorio fue creado correctamente.

## Laboratorio 5

```bash
mateo@equipo:~$ mkdir fotos videos música
mateo@equipo:~$ ls
archivo1.txt  archivo2.txt  archivo3.txt  documentos  fotos  música  prueba.txt  videos
```

### Análisis

* El comando `mkdir fotos videos música` crea los tres directorios en una sola línea.
* `ls` muestra que los directorios fueron creados exitosamente junto con otros archivos y directorios.

## Laboratorio 6

```bash
mateo@equipo:~$ mkdir -p proyecto/src/main
mateo@equipo:~$ tree proyecto
proyecto
└── src
    └── main

3 directories, 0 files
```

### Análisis

* La opción `-p` permite crear directorios anidados en un solo comando.
* `tree proyecto` muestra la estructura completa del directorio `proyecto`.
* Si `tree` no estuviera instalado, se podría usar `ls -R proyecto` para ver la estructura recursiva.

## Laboratorio 7

```bash
mateo@equipo:~$ mkdir trabajo
mateo@equipo:~$ touch trabajo/informe.txt trabajo/notas.md
mateo@equipo:~$ ls trabajo
informe.txt  notas.md
```

### Análisis

* Se crea un directorio `trabajo`.
* Se crean dos archivos dentro del directorio.
* El comando `ls trabajo` confirma que ambos archivos existen en la carpeta.

## Laboratorio 8

```bash
mateo@equipo:~$ mkdir -p biblioteca/{libros,revistas,artículos}
mateo@equipo:~$ touch biblioteca/libros/novela.txt biblioteca/revistas/ciencia.md
mateo@equipo:~$ tree biblioteca
biblioteca
├── artículos
├── libros
│   └── novela.txt
└── revistas
    └── ciencia.md
```

### Análisis

* Se crea una estructura de directorios anidados en `biblioteca`.
* Los archivos se crean en sus respectivos subdirectorios.
* El comando `tree` muestra claramente la estructura creada con archivos dentro.

## Laboratorio 9

```bash
mateo@equipo:~$ mkdir mi_proyecto
mateo@equipo:~$ cd mi_proyecto
mateo@equipo:~/mi_proyecto$ mkdir codigo documentacion recursos
mateo@equipo:~/mi_proyecto$ touch codigo/main.py codigo/config.json
mateo@equipo:~/mi_proyecto$ touch documentacion/README.md
mateo@equipo:~/mi_proyecto$ tree
.
├── codigo
│   ├── config.json
│   └── main.py
├── documentacion
│   └── README.md
└── recursos
```

### Análisis

* Se crea una estructura de proyecto organizada con carpetas para código, documentación y recursos.
* Los archivos se distribuyen adecuadamente según su función.
* El comando `tree` confirma la correcta creación de la estructura.

# Lección 2

## Laboratorio 1
```bash
mateo@equipo:~$ pwd
/home/mateo
```

### Análisis de la Ruta:
La ruta /home/mateo se puede descomponer así:

/ : El directorio raíz del sistema.

home : Contiene los directorios personales de los usuarios.

mateo : Es el directorio personal del usuario Mateo. Aquí se encuentran mis archivos, configuraciones y demás documentos personales.

Esta ruta indica que actualmente se está trabajando dentro del directorio personal del usuario Mateo.

## Laboratorio 2
```bash
mateo@equipo:~$ cd /
mateo@equipo:/$ pwd
/
mateo@equipo:/$ ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
```

### Análisis:
El comando cd / lleva al usuario al directorio raíz del sistema.

Al ejecutar pwd, se muestra /, indicando que efectivamente se encuentra en la raíz.

El comando ls muestra los directorios principales del sistema, cada uno con un propósito específico, como:

bin: programas ejecutables del sistema.

etc: archivos de configuración.

home: directorios personales de los usuarios.

usr: aplicaciones y utilidades del sistema.

var: archivos variables como logs, colas de impresión, etc.

## Laboratorio 3

```bash
mateo@equipo:~$ cd /home
mateo@equipo:/home$ pwd
/home
mateo@equipo:/home$ cd mateo
mateo@equipo:/home/mateo$ pwd
/home/mateo
```

### Análisis:
Con cd /home, el usuario navega al directorio principal donde se almacenan los perfiles de usuario.

Con pwd, se confirma que efectivamente está en /home.

Finalmente, con cd mateo, el usuario accede a su propio directorio personal.

## Laboratorio 4

```bash
mateo@equipo:~$ cd /home
mateo@equipo:/home$ cd mateo
mateo@equipo:/home/mateo$ pwd
/home/mateo
mateo@equipo:/home/mateo$ cd Documentos
mateo@equipo:/home/mateo/Documentos$ pwd
/home/mateo/Documentos
```


### Análisis:
Primero, el usuario navega al directorio /home.

Luego usa cd mateo, una ruta relativa para ingresar a su carpeta personal.

Finalmente, entra al subdirectorio Documentos usando otra ruta relativa, sin necesidad de especificar /home/mateo/Documentos.

Esto demuestra cómo las rutas relativas permiten moverse en el sistema de archivos sin especificar la ruta completa.

## Laboratorio 5

```bash
mateo@equipo:~$ pwd
/home/mateo
mateo@equipo:~$ cd /tmp
mateo@equipo:/tmp$ pwd
/tmp
mateo@equipo:/tmp$ cd -
/home/mateo
mateo@equipo:~$ cd -
/tmp
mateo@equipo:/tmp$ cd -
/home/mateo
```

### Análisis:
El comando cd /tmp cambia al directorio temporal del sistema.

cd - alterna entre el directorio actual y el anterior. En este caso, alterna entre /home/mateo y /tmp.

Esta herramienta es útil para cambiar rápidamente entre dos ubicaciones sin tener que escribir rutas completas.

## Laboratorio 6

```bash
mateo@equipo:/tmp$ cd ~
mateo@equipo:~$ pwd
/home/mateo
mateo@equipo:~$ touch prueba.txt
mateo@equipo:~$ ls
prueba.txt
```

### Análisis:
Con cd ~, el usuario accede directamente a su directorio personal sin importar su ubicación anterior.

pwd muestra que se encuentra en /home/mateo.

touch prueba.txt crea un archivo dentro de su directorio personal.

El archivo aparece listado con ls, confirmando su creación.

## Laboratorio 7

```bash
mateo@equipo:~$ cd /home/mateo/Documentos
mateo@equipo:/home/mateo/Documentos$ cd ..
mateo@equipo:/home/mateo$ pwd
/home/mateo
mateo@equipo:/home/mateo$ cd ../..
mateo@equipo:/home$ pwd
/home
```

### Análisis:
Con cd /home/mateo/Documentos, Mateo accede a su carpeta Documentos.

El comando cd .. sube un nivel, regresando a /home/mateo.

Luego, con cd ../.., sube dos niveles más, llegando a /home.

pwd confirma la ubicación actual en cada paso, mostrando cómo cd .. permite moverse hacia directorios padres en la jerarquía.

## Laboratorio 8

```bash
mateo@equipo:~$ cd /home
mateo@equipo:/home$ cd mateo/Descargas
mateo@equipo:/home/mateo/Descargas$ cd /home
mateo@equipo:/home$ pwd
/home
```

### Análisis:
El usuario inicia en /home.

Con cd mateo/Descargas, navega usando una ruta relativa: parte desde la ubicación actual y se dirige al subdirectorio mateo/Descargas.

Posteriormente, con cd /home, vuelve al directorio /home usando una ruta absoluta: esta comienza desde el directorio raíz (/) e indica el camino completo.

Diferencias entre rutas relativas y absolutas:
Ruta relativa: Especifica una ubicación partiendo del directorio actual. Ejemplo: cd mateo/Descargas.

Ruta absoluta: Define la ruta completa desde el directorio raíz del sistema. Ejemplo: cd /home/mateo/Descargas.

Las rutas relativas son útiles para movimientos dentro de una estructura conocida, mientras que las absolutas aseguran llegar a un destino específico desde cualquier ubicación.

## Laboratorio 9

```bash
mateo@equipo:~$ mkdir ~/pruebas
mateo@equipo:~$ cd ~/pruebas
mateo@equipo:~/pruebas$ mkdir nivel1
mateo@equipo:~/pruebas$ cd nivel1
mateo@equipo:~/pruebas/nivel1$ pwd
/home/mateo/pruebas/nivel1
```

### Análisis:
mkdir ~/pruebas crea un nuevo directorio llamado pruebas en el directorio personal del usuario.

cd ~/pruebas permite ingresar al nuevo directorio.

Dentro de pruebas, se crea un subdirectorio llamado nivel1 con mkdir nivel1.

Luego, se accede a este nuevo subdirectorio con cd nivel1.

El comando pwd confirma la ubicación final en /home/mateo/pruebas/nivel1.

## Laboratorio 10

```bash
mateo@equipo:~$ ls -a
.  ..  .bashrc  .config  .local  prueba.txt
mateo@equipo:~$ cd .config
mateo@equipo:~/.config$ pwd
/home/mateo/.config
```

### Análisis:
El comando ls -a muestra todos los archivos y carpetas, incluidos los ocultos, que comienzan con un punto (.).

.config es uno de esos directorios ocultos, normalmente usado para guardar configuraciones de programas.

Con cd .config, el usuario accede al directorio.

pwd confirma la nueva ubicación como /home/mateo/.config.

# Lección 3

## Laboratorio 1

```bash
mateo@equipo:~$ ls
Documentos  Descargas  Imágenes  Música  pruebas  prueba.txt
```
### Análisis:
El comando ls lista los archivos y directorios presentes en el directorio actual del usuario.

En este caso, se muestran varias carpetas estándar como Documentos, Descargas, Imágenes, Música, así como una carpeta pruebas creada en laboratorios anteriores y el archivo prueba.txt.

Pregunta de Reflexión:
¿Qué sucede si ejecutas ls en un directorio vacío?

Cuando se ejecuta ls en un directorio vacío, no se muestra ningún resultado. La terminal simplemente retorna al prompt sin errores, lo cual indica que no hay archivos ni carpetas visibles en ese directorio.

## Laboratorio 2

```bash
mateo@equipo:~$ ls -a
.  ..  .bashrc  .config  .local  .mi_archivo_secreto  Documentos  Descargas  Imágenes  Música  pruebas  prueba.txt
mateo@equipo:~$ touch .mi_archivo_secreto
mateo@equipo:~$ ls -a
.  ..  .bashrc  .config  .local  .mi_archivo_secreto  Documentos  Descargas  Imágenes  Música  pruebas  prueba.txt
```
### Análisis:
El comando ls -a muestra todos los archivos, incluyendo los ocultos (que comienzan con un punto .).

Se crea el archivo oculto .mi_archivo_secreto con touch.

Al ejecutar nuevamente ls -a, el archivo aparece listado junto con otros ocultos como .bashrc y .config.

Pregunta de Reflexión:
¿Por qué crees que algunos archivos están ocultos por defecto?

Los archivos ocultos suelen contener configuraciones de usuario o del sistema que no necesitan ser modificadas frecuentemente. Ocultarlos ayuda a mantener el entorno de trabajo limpio y evita modificaciones accidentales por parte del usuario.

## Laboratorio 3

```bash
mateo@equipo:~$ touch prueba.txt
mateo@equipo:~$ ls -l
total 4
drwxr-xr-x 2 mateo mateo 4096 jan 12 15:00 Documentos
drwxr-xr-x 2 mateo mateo 4096 jan 12 15:00 Descargas
drwxr-xr-x 2 mateo mateo 4096 jan 12 15:00 Imágenes
drwxr-xr-x 2 mateo mateo 4096 jan 12 15:00 Música
drwxr-xr-x 3 mateo mateo 4096 may 23 12:01 pruebas
-rw-r--r-- 1 mateo mateo    0 may 23 12:05 prueba.txt
```

### Análisis:
El comando ls -l proporciona una vista detallada de los archivos y directorios.

Cada línea incluye:

Permisos (-rw-r--r--),

Número de enlaces,

Propietario (mateo),

Grupo (mateo),

Tamaño en bytes,

Fecha y hora de última modificación,

Nombre del archivo o directorio.

Ejercicio:
Archivo creado: prueba.txt

¿Qué permisos tiene el archivo?
-rw-r--r--
Esto indica que:

El propietario puede leer y escribir.

El grupo y otros usuarios solo pueden leer.

¿Quién es el propietario?
mateo, tanto como usuario como grupo.

## Laboratorio 4

```bash
mateo@equipo:~$ dd if=/dev/zero of=archivo_grande bs=1M count=10
10+0 records in
10+0 records out
10485760 bytes (10 MB, 10 MiB) copied, 0.0123456 s, 850 MB/s
mateo@equipo:~$ ls -lh
total 11M
-rw-r--r-- 1 mateo mateo  10M may 23 12:10 archivo_grande
drwxr-xr-x 2 mateo mateo 4.0K jan 12 15:00 Documentos
drwxr-xr-x 2 mateo mateo 4.0K jan 12 15:00 Descargas
drwxr-xr-x 2 mateo mateo 4.0K jan 12 15:00 Imágenes
drwxr-xr-x 2 mateo mateo 4.0K jan 12 15:00 Música
drwxr-xr-x 3 mateo mateo 4.0K may 23 12:01 pruebas
-rw-r--r-- 1 mateo mateo    0 may 23 12:05 prueba.txt
```

### Análisis:
El comando ls -lh muestra la lista de archivos con detalles y tamaños en unidades comprensibles como KB, MB, GB.

El archivo archivo_grande aparece con un tamaño de 10M, lo que indica que pesa 10 megabytes.

Pregunta de Reflexión:
¿Por qué es útil mostrar el tamaño en formato legible?

Mostrar los tamaños en KB, MB o GB facilita la lectura y comprensión para el usuario. Es más práctico y claro que interpretar cantidades en bytes, especialmente cuando se manejan archivos grandes o se necesita evaluar rápidamente el uso del almacenamiento.

## Laboratorio 5

```bash
mateo@equipo:~$ ls -lt
total 11M
-rw-r--r-- 1 mateo mateo  10M may 23 12:10 archivo_grande
-rw-r--r-- 1 mateo mateo    0 may 23 12:05 prueba.txt
drwxr-xr-x 3 mateo mateo 4.0K may 23 12:01 pruebas
drwxr-xr-x 2 mateo mateo 4.0K may 23 12:00 Documentos
drwxr-xr-x 2 mateo mateo 4.0K may 23 12:00 Descargas
drwxr-xr-x 2 mateo mateo 4.0K may 23 12:00 Imágenes
drwxr-xr-x 2 mateo mateo 4.0K may 23 12:00 Música

mateo@equipo:~$ echo "nuevo contenido" >> prueba.txt
mateo@equipo:~$ ls -lt
total 11M
-rw-r--r-- 1 mateo mateo   17 may 23 12:15 prueba.txt
-rw-r--r-- 1 mateo mateo  10M may 23 12:10 archivo_grande
drwxr-xr-x 3 mateo mateo 4.0K may 23 12:01 pruebas
drwxr-xr-x 2 mateo mateo 4.0K may 23 12:00 Documentos
drwxr-xr-x 2 mateo mateo 4.0K may 23 12:00 Descargas
drwxr-xr-x 2 mateo mateo 4.0K may 23 12:00 Imágenes
drwxr-xr-x 2 mateo mateo 4.0K may 23 12:00 Música
```

### Análisis:
El comando ls -lt ordena los archivos y directorios por fecha de modificación, del más reciente al más antiguo.

Al modificar prueba.txt con echo, su fecha de modificación cambia.

Al volver a ejecutar ls -lt, prueba.txt aparece en primer lugar, indicando que es el archivo más recientemente modificado.

Pregunta de Reflexión:
¿Dónde aparece el archivo modificado en la lista?

El archivo modificado aparece al inicio de la lista, lo que facilita identificar los cambios más recientes en un directorio.

## Laboratorio 6

```bash
mateo@equipo:~$ mkdir -p mi_directorio/subdirectorio1/subdirectorio2
mateo@equipo:~$ touch mi_directorio/archivo1.txt
mateo@equipo:~$ touch mi_directorio/subdirectorio1/archivo2.txt
mateo@equipo:~$ ls -R
.:
mi_directorio

./mi_directorio:
archivo1.txt  subdirectorio1

./mi_directorio/subdirectorio1:
archivo2.txt  subdirectorio2

./mi_directorio/subdirectorio1/subdirectorio2:
```

### Análisis:
Se crea una jerarquía de carpetas y archivos dentro de mi_directorio.

El comando ls -R muestra todos los archivos y subdirectorios recursivamente, lo cual incluye cada nivel dentro de la estructura.

La salida indica en qué ruta se encuentra cada grupo de archivos/directorios.

Pregunta de Reflexión:
¿Cómo ayuda la opción -R a explorar directorios grandes?

La opción -R es muy útil para inspeccionar el contenido completo de un directorio y todos sus subdirectorios sin tener que ingresar manualmente a cada uno. Esto facilita la exploración y auditoría de estructuras complejas o profundas en el sistema de archivos.

## Laboratorio 7

```bash
mateo@equipo:~$ mkdir carpeta_visible
mateo@equipo:~$ mkdir .carpeta_oculta
mateo@equipo:~$ touch archivo1.txt
mateo@equipo:~$ touch .archivo_oculto.txt
mateo@equipo:~$ ls -lah
total 28K
drwxr-xr-x 6 mateo mateo 4.0K may 23 13:00 .
drwxr-xr-x 3 root  root  4.0K may 23 12:00 ..
-rw-r--r-- 1 mateo mateo    0 may 23 13:00 .archivo_oculto.txt
drwxr-xr-x 2 mateo mateo 4.0K may 23 13:00 .carpeta_oculta
-rw-r--r-- 1 mateo mateo    0 may 23 13:00 archivo1.txt
drwxr-xr-x 2 mateo mateo 4.0K may 23 13:00 carpeta_visible
```

### Análisis:
ls -lah combina tres opciones:

l: listado detallado (permisos, propietario, tamaño, fecha).

a: muestra archivos ocultos (los que empiezan con .).

h: muestra tamaños en formato legible (KB, MB, etc.).

Esta combinación permite ver todo el contenido del directorio, incluidos los ocultos, con detalles útiles para administración y diagnóstico.

Pregunta de Reflexión:
¿Qué ventajas tiene combinar estas opciones?

Combinar estas opciones permite obtener una visión completa del contenido del directorio, útil para auditorías, limpieza, backups, y comprensión de la estructura del sistema.

## Laboratorio 8

```bash
mateo@equipo:~$ mkdir carpeta1 carpeta2
mateo@equipo:~$ touch archivo1.txt archivo2.txt
mateo@equipo:~$ ls -d */
carpeta1/  carpeta2/
```

### Análisis:
El comando ls -d */ muestra solo los directorios terminados en /.

No lista archivos, solo carpetas, lo que facilita identificar rápidamente los directorios en un lugar.

Esto es útil para administrar o navegar entre directorios sin el ruido de los archivos.

Pregunta de Reflexión:
¿En qué situaciones es útil listar solo directorios?

Es útil cuando se quiere ver la estructura de carpetas para navegación, respaldos selectivos, o para evitar modificar archivos accidentales cuando se trabaja con directorios.

## Laboratorio 9

```bash
mateo@equipo:~$ ls -l
-rw-r--r-- 1 mateo mateo 0 may 23 14:00 archivo1.txt
mateo@equipo:~$ chmod u+x archivo1.txt
mateo@equipo:~$ ls -l
-rwxr--r-- 1 mateo mateo 0 may 23 14:01 archivo1.txt
```

### Análisis:
El primer ls -l muestra que archivo1.txt tiene permisos de lectura y escritura para el usuario, y solo lectura para grupo y otros (-rw-r--r--).

Después de ejecutar chmod u+x archivo1.txt, se añade permiso de ejecución para el propietario (-rwxr--r--).

Esto significa que ahora el usuario “mateo” puede ejecutar el archivo además de leerlo y escribirlo.

Pregunta de Reflexión:
¿Qué importancia tienen los permisos en la gestión de archivos en Linux?

Los permisos son cruciales para la seguridad y el control de acceso, asegurando que solo usuarios autorizados puedan leer, modificar o ejecutar archivos, previniendo acciones no deseadas o maliciosas.

## Laboratorio 10

```bash
mateo@equipo:~$ mkdir -p proyecto/{documentos,imagenes,temp}
mateo@equipo:~$ touch proyecto/documentos/reporte.txt
mateo@equipo:~$ touch proyecto/imagenes/foto.jpg
mateo@equipo:~$ touch proyecto/temp/archivo_temporal
mateo@equipo:~$ touch proyecto/.configuracion
mateo@equipo:~$ ls proyecto
.configuracion  documentos  imagenes  temp
mateo@equipo:~$ ls -a proyecto
.  ..  .configuracion  documentos  imagenes  temp
mateo@equipo:~$ ls -lh proyecto
total 0
-rw-r--r-- 1 mateo mateo 0 may 23 14:20 .configuracion
drwxr-xr-x 2 mateo mateo 40 may 23 14:20 documentos
drwxr-xr-x 2 mateo mateo 40 may 23 14:20 imagenes
drwxr-xr-x 2 mateo mateo 40 may 23 14:20 temp
mateo@equipo:~$ ls -d proyecto/*/
proyecto/documentos/  proyecto/imagenes/  proyecto/temp/
```

### Análisis:
Se creó una estructura organizada con archivos y directorios.

ls -a muestra todos los archivos, incluyendo el oculto .configuracion.

ls -lh muestra permisos, tamaños legibles y propietarios.

ls -d */ lista solo directorios, útil para ver la estructura general.

Pregunta de Reflexión:
¿Qué opción usarías para encontrar rápidamente un archivo oculto importante?

Usaría ls -a para listar todos los archivos, incluyendo los ocultos, que por defecto no se muestran y podrían contener configuraciones o datos importantes.

# Lección 4

## Laboratorio 1: Copiar un archivo simple

```bash
mateo@equipo:~$ touch archivo1.txt
mateo@equipo:~$ cp archivo1.txt copia_archivo1.txt
mateo@equipo:~$ ls
archivo1.txt  copia_archivo1.txt
```

### Análisis:
El comando touch archivo1.txt crea un archivo vacío llamado archivo1.txt.

Luego, cp archivo1.txt copia_archivo1.txt crea una copia exacta del archivo original con un nombre diferente.

ls confirma que ambos archivos existen en el mismo directorio.

Preguntas:
¿Qué sucede si intentas copiar un archivo que no existe?
Aparece un mensaje de error indicando que el archivo fuente no se encontró, y no se realiza ninguna copia.

¿Qué pasa si el archivo de destino ya existe?
El archivo de destino se sobrescribe sin advertencia, reemplazando el contenido previo.

## Laboratorio 2: Copiar un archivo a otro directorio

```bash
mateo@equipo:~$ mkdir documentos
mateo@equipo:~$ cp archivo1.txt documentos/
mateo@equipo:~$ cd documentos
mateo@equipo:~/documentos$ ls
archivo1.txt
```

### Análisis:
mkdir documentos crea un nuevo directorio llamado documentos.

cp archivo1.txt documentos/ copia el archivo al nuevo directorio.

cd documentos seguido de ls permite verificar que el archivo fue copiado exitosamente al nuevo destino.

Preguntas:
¿Qué sucede si el directorio de destino no existe?
El comando cp mostrará un error indicando que no se puede encontrar el directorio de destino, y no realizará la copia.

¿Cómo puedes copiar un archivo a un directorio fuera del directorio actual?
Usando una ruta relativa (por ejemplo, ../otro_directorio/) o una ruta absoluta (por ejemplo, /home/mateo/otro_directorio/).

## Laboratorio 3: Copiar múltiples archivos

```bash
mateo@equipo:~$ touch archivo2.txt archivo3.txt archivo4.txt
mateo@equipo:~$ cp archivo2.txt archivo3.txt archivo4.txt documentos/
mateo@equipo:~$ ls documentos/
archivo1.txt  archivo2.txt  archivo3.txt  archivo4.txt
```

### Análisis:
touch archivo2.txt archivo3.txt archivo4.txt crea tres archivos nuevos en el directorio actual.

cp archivo2.txt archivo3.txt archivo4.txt documentos/ copia los tres archivos al directorio documentos.

ls documentos/ muestra que todos los archivos fueron copiados correctamente.

Preguntas:
¿Qué sucede si uno de los archivos no existe?
El comando cp mostrará un mensaje de error y no copiará ningún archivo, a menos que uses la opción --no-clobber para ignorar errores.
Ejemplo del error:

yaml
Copiar
Editar
cp: no se puede efectuar `stat' sobre 'archivoX.txt': No existe el archivo o el directorio
¿Cómo puedes copiar todos los archivos .txt de un directorio?
Usando un comodín (wildcard) con el patrón *.txt, por ejemplo:

bash
Copiar
Editar
cp *.txt documentos/
Esto copiará todos los archivos con extensión .txt en el directorio actual al directorio documentos/.

## Laboratorio 4: Copiar un directorio completo

```bash
mateo@equipo:~$ mkdir proyectos
mateo@equipo:~$ touch proyectos/archivo5.txt proyectos/archivo6.txt
mateo@equipo:~$ cp -r proyectos proyectos_copia
mateo@equipo:~$ ls proyectos_copia/
archivo5.txt  archivo6.txt
```

### Análisis:
mkdir proyectos crea un nuevo directorio.

touch proyectos/archivo5.txt proyectos/archivo6.txt crea archivos dentro de proyectos.

cp -r proyectos proyectos_copia copia de forma recursiva todo el contenido del directorio proyectos al nuevo directorio proyectos_copia.

ls proyectos_copia/ muestra que los archivos fueron copiados correctamente.

Preguntas:
¿Qué sucede si omites la opción -r al copiar un directorio?
El comando cp devolverá un error como:

bash
Copiar
Editar
cp: omitiendo el directorio 'proyectos'
Esto ocurre porque, sin -r, cp no puede manejar directorios.

¿Cómo puedes copiar solo ciertos archivos dentro de un directorio?
Puedes usar comodines. Por ejemplo, para copiar solo archivos .txt de proyectos:

bash
Copiar
Editar
cp proyectos/*.txt otro_directorio/
También puedes especificar los archivos individualmente:

bash
Copiar
Editar
cp proyectos/archivo5.txt proyectos/archivo6.txt otro_directorio/

## Laboratorio 5: Forzar la sobrescritura de archivos

```bash
mateo@equipo:~$ touch archivo7.txt
mateo@equipo:~$ cp archivo7.txt documentos/
mateo@equipo:~$ cp -f archivo7.txt documentos/
```

### Análisis:
touch archivo7.txt crea un archivo vacío llamado archivo7.txt.

cp archivo7.txt documentos/ lo copia por primera vez al directorio documentos.

cp -f archivo7.txt documentos/ vuelve a copiarlo y fuerza la sobrescritura, sin pedir confirmación.

Esta opción es útil cuando se automatizan tareas o se quiere evitar cualquier interrupción por archivos ya existentes.

Preguntas
¿Qué sucede si no usas la opción -f?
Si el archivo de destino ya existe, cp lo sobrescribe por defecto sin preguntar. Sin embargo, si tu entorno de terminal tiene cp configurado como alias con -i (interactivo), se te pedirá confirmación antes de sobrescribir.

¿Cómo puedes evitar que se sobrescriba un archivo existente?
Puedes usar la opción -n (no sobrescribir archivos existentes):

bash
Copiar
Editar
cp -n archivo7.txt documentos/
Esto copiará el archivo solo si no existe en el destino.

bash
Copiar
Editar

## Laboratorio 6: Mostrar mensajes detallados

```bash
mateo@equipo:~$ cp -v archivo7.txt documentos/
'archivo7.txt' -> 'documentos/archivo7.txt'
```

### Análisis:
La opción -v (verbose) muestra en pantalla exactamente qué archivo se está copiando y a dónde. Esto es útil para verificar visualmente el progreso y confirmar que la operación se realiza correctamente.

En este caso, el sistema indica que el archivo archivo7.txt fue copiado al directorio documentos.

Preguntas
¿Qué información adicional muestra la opción -v?
Muestra el nombre del archivo origen y su ruta de destino. Esto ayuda a confirmar que el archivo fue copiado correctamente.

¿Cómo puedes combinar -v con otras opciones como -f?
Puedes combinarlas fácilmente en un solo comando. Por ejemplo:

bash
Copiar
Editar
cp -fv archivo7.txt documentos/
Esto forzará la sobrescritura si el archivo ya existe y mostrará un mensaje detallado de la operación realizada.

## Laboratorio 7: Preservar atributos de archivos

```bash
mateo@equipo:~$ touch archivo8.txt

mateo@equipo:~$ touch -d "2022-01-01" archivo8.txt

mateo@equipo:~$ cp -p archivo8.txt copia_archivo8.txt

mateo@equipo:~$ ls -l archivo8.txt copia_archivo8.txt
-rw-r--r-- 1 mateo mateo 0 ene  1  2022 archivo8.txt
-rw-r--r-- 1 mateo mateo 0 ene  1  2022 copia_archivo8.txt
```

### Análisis:
La opción -p preserva los atributos del archivo original durante la copia. En este ejemplo, tanto la fecha de modificación, los permisos y el propietario del archivo original se mantienen intactos en la copia.

Preguntas
¿Qué atributos se preservan con la opción -p?
Se preservan los siguientes atributos:

Fecha de modificación

Permisos (lectura, escritura, ejecución)

Propietario y grupo

¿Qué sucede si no usas la opción -p?
El archivo copiado tomará los atributos por defecto:

La fecha y hora actuales como fecha de modificación.

Los permisos por defecto del usuario actual.

El usuario actual será el propietario del nuevo archivo, aunque se mantenga en el mismo sistema.

## Laboratorio 8
```bash
Copiar
Editar
mateo@equipo:~$ touch archivo_a.txt archivo_b.txt archivo_c.txt
mateo@equipo:~$ cp archivo_*.txt documentos/
mateo@equipo:~$ ls documentos/
archivo_a.txt  archivo_b.txt  archivo_c.txt
```
### Análisis
En este laboratorio se usó un patrón con * para copiar solo los archivos cuyos nombres comienzan con archivo_ y terminan con .txt al directorio documentos.

El patrón archivo_*.txt selecciona todos los archivos que empiezan con archivo_ y terminan con .txt.

Esto permite copiar múltiples archivos que cumplen ese criterio sin escribir cada nombre explícitamente.

## Laboratorio 9
```bash
Copiar
Editar
mateo@equipo:~$ cp /media/usb/archivo_usb.txt .
mateo@equipo:~$ ls
archivo_usb.txt  archivo_a.txt  archivo_b.txt  archivo_c.txt  documentos
```

### Análisis
En este laboratorio se copia un archivo desde un dispositivo externo (USB) montado en /media/usb al directorio actual ..

La ruta absoluta /media/usb/archivo_usb.txt indica la ubicación del archivo en el USB.

El punto . representa el directorio actual.

Para que la copia funcione, el dispositivo USB debe estar montado correctamente.

Preguntas
¿Qué sucede si el dispositivo USB no está montado?
El comando cp fallará con un error indicando que la ruta no existe o no se puede encontrar el archivo.

¿Cómo puedes verificar las ubicaciones de los dispositivos conectados?
Puedes usar comandos como lsblk, df -h o mount para listar los dispositivos y sus puntos de montaje.

---

## Laboratorio 10

```bash
mateo@equipo:~$ cp archivo_inexistente.txt documentos/
cp: no se puede copiar 'archivo_inexistente.txt' a 'documentos/': No existe el archivo o el directorio

mateo@equipo:~$ cp archivo1.txt directorio_inexistente/
cp: no se puede crear el archivo regular 'directorio_inexistente/archivo1.txt': No existe el archivo o el directorio
```

### Análisis

* Cuando intentas copiar un archivo que no existe, el comando muestra un error indicando que no puede encontrar el archivo de origen.
* Si el directorio de destino no existe, el comando da un error indicando que no puede crear el archivo porque la ruta no existe.
* Para corregir estos errores, debes asegurarte que:

  * El archivo de origen exista.
  * El directorio destino exista o crearlo antes con `mkdir`.

### Preguntas

* ¿Qué mensaje de error recibes cuando el archivo de origen no existe?
  `cp: no se puede copiar 'archivo_inexistente.txt' a 'documentos/': No existe el archivo o el directorio`

* ¿Qué mensaje de error recibes cuando el directorio de destino no existe?
  `cp: no se puede crear el archivo regular 'directorio_inexistente/archivo1.txt': No existe el archivo o el directorio`

# Lección 5

## Laboratorio 1

```bash
mateo@equipo:~$ touch prueba.txt
mateo@equipo:~$ mv prueba.txt archivo_renombrado.txt
mateo@equipo:~$ ls
archivo_renombrado.txt
```

### Análisis

* Se creó un archivo nuevo llamado `prueba.txt`.
* Se renombró correctamente a `archivo_renombrado.txt` con el comando `mv`.
* El archivo permanece en el mismo directorio, solo cambia su nombre.


## Laboratorio 2

```bash
mateo@equipo:~$ mkdir temporal
mateo@equipo:~$ mv temporal archivos_temporales
mateo@equipo:~$ ls
archivos_temporales
```

### Análisis

* Se creó el directorio `temporal`.
* Se renombró correctamente a `archivos_temporales` con el comando `mv`.
* `mv` funciona igual para archivos y directorios, cambiando su nombre sin moverlos.

## Laboratorio 3

```bash
mateo@equipo:~$ mkdir documentos
mateo@equipo:~$ touch informe.txt
mateo@equipo:~$ mv informe.txt documentos/
mateo@equipo:~$ ls documentos/
informe.txt
```

### Análisis

* Se creó el directorio `documentos`.
* Se creó el archivo `informe.txt`.
* Se movió correctamente el archivo al directorio `documentos` usando `mv`.
* `mv` sirve tanto para renombrar como para mover archivos o directorios a otra ubicación.

## Laboratorio 4

```bash
mateo@equipo:~$ touch archivo1.txt archivo2.txt archivo3.txt
mateo@equipo:~$ mkdir respaldos
mateo@equipo:~$ mv *.txt respaldos/
mateo@equipo:~$ ls respaldos/
archivo1.txt  archivo2.txt  archivo3.txt
```

### Análisis

* Se crearon tres archivos con extensión `.txt`.
* Se creó el directorio `respaldos`.
* Se movieron todos los archivos `.txt` al directorio `respaldos` usando el patrón `*.txt`.
* Esto demuestra cómo mover múltiples archivos usando comodines (wildcards) en `mv`.

## Laboratorio 5

```bash
mateo@equipo:~$ touch datos_originales.txt
mateo@equipo:~$ mkdir backup
mateo@equipo:~$ mv datos_originales.txt backup/datos_backup.txt
mateo@equipo:~$ ls backup/
datos_backup.txt
```

### Análisis

* Se creó el archivo `datos_originales.txt`.
* Se creó el directorio `backup`.
* El archivo fue movido al directorio `backup` y renombrado a `datos_backup.txt` en un solo paso.
* Esto muestra cómo `mv` puede mover y cambiar el nombre simultáneamente con una sola instrucción.

## Laboratorio 6

```bash
mateo@equipo:~$ touch archivo_existente.txt
mateo@equipo:~$ mkdir documento
mateo@equipo:~$ touch documento/archivo_existente.txt
mateo@equipo:~$ mv -i archivo_existente.txt documento/
mv: overwrite 'documento/archivo_existente.txt'? n
mateo@equipo:~$ ls documento/
archivo_existente.txt
```

### Análisis

* Se crearon dos archivos con el mismo nombre, uno en el directorio actual y otro en `documento`.
* Al intentar mover el archivo con `mv -i`, se pidió confirmación para sobrescribir.
* Al responder `n` (no), el archivo original en `documento` no fue sobrescrito.
* La opción `-i` es útil para evitar sobrescrituras accidentales al mover archivos.

## Laboratorio 7

```bash
mateo@equipo:~$ touch archivo_viejo.txt
mateo@equipo:~$ echo "Contenido viejo" > archivo_viejo.txt
mateo@equipo:~$ mkdir respaldo
mateo@equipo:~$ cp archivo_viejo.txt respaldo/
mateo@equipo:~$ echo "Contenido nuevo" > archivo_viejo.txt
mateo@equipo:~$ mv -u archivo_viejo.txt respaldo/
mateo@equipo:~$ cat respaldo/archivo_viejo.txt
Contenido nuevo
```

### Análisis

* Se creó un archivo `archivo_viejo.txt` con contenido inicial.
* Se copió a la carpeta `respaldo`.
* Luego se modificó el archivo original con contenido nuevo.
* Usando `mv -u`, solo se movió el archivo si el original era más reciente que la copia.
* El archivo en `respaldo` quedó actualizado con el contenido nuevo.
* La opción `-u` previene mover archivos innecesariamente si la copia es igual o más nueva.

## Laboratorio 8

```bash
mateo@equipo:~$ touch archivo_absoluto.txt
mateo@equipo:~$ mv archivo_absoluto.txt /tmp/
mateo@equipo:~$ ls /tmp/
archivo_absoluto.txt
```

### Análisis

* Se creó un archivo `archivo_absoluto.txt` en el directorio actual.
* Se movió usando una ruta absoluta `/tmp/`, que es un directorio estándar para archivos temporales.
* La verificación confirma que el archivo se encuentra ahora en `/tmp/`.
* Usar rutas absolutas permite mover archivos a cualquier lugar del sistema sin importar el directorio actual.

## Laboratorio 9

```bash
mateo@equipo:~$ touch "mi archivo.txt"
mateo@equipo:~$ mkdir destino
mateo@equipo:~$ mv "mi archivo.txt" destino/
mateo@equipo:~$ ls destino/
mi archivo.txt
```

### Análisis

* El archivo con espacios en el nombre fue creado correctamente usando comillas.
* El comando `mv` también usó comillas para manejar el nombre con espacios.
* Se movió el archivo sin problemas al directorio `destino`.
* Alternativamente, se puede usar el carácter de escape `\` para espacios (ejemplo: `mi\ archivo.txt`).
* Manejar adecuadamente los espacios en nombres de archivos es clave para evitar errores en la terminal.

# Lección 6

## Laboratorio 1

```bash
mateo@equipo:~$ touch archivo1.txt
mateo@equipo:~$ ls
archivo1.txt
mateo@equipo:~$ rm archivo1.txt
mateo@equipo:~$ ls
mateo@equipo:~$
```

### Análisis

* Se creó correctamente el archivo `archivo1.txt`.
* El archivo aparece listado al usar `ls`.
* El comando `rm archivo1.txt` elimina el archivo.
* Después de la eliminación, el archivo ya no aparece en la lista.
* `rm` elimina archivos de forma permanente sin pasar por la papelera.

## Laboratorio 2

```bash
mateo@equipo:~$ touch archivoA.txt archivoB.txt archivoC.txt
mateo@equipo:~$ ls
archivoA.txt  archivoB.txt  archivoC.txt
mateo@equipo:~$ rm archivoA.txt archivoB.txt archivoC.txt
mateo@equipo:~$ ls
mateo@equipo:~$
```

### Análisis

* Se crearon los tres archivos correctamente.
* El comando `rm` con múltiples archivos permite eliminar varios archivos en una sola ejecución.
* Después de ejecutar `rm` con los tres archivos, ninguno aparece en el listado.
* `rm` puede aceptar múltiples argumentos para eliminar varios archivos rápidamente.

## Laboratorio 3

```bash
mateo@equipo:~$ touch importante.txt
mateo@equipo:~$ rm -i importante.txt
rm: remove regular file 'importante.txt'? y
mateo@equipo:~$ ls
mateo@equipo:~$
```

### Análisis

* El flag `-i` hace que `rm` pregunte confirmación antes de eliminar cada archivo.
* Esto previene borrados accidentales.
* Si respondes `y`, el archivo se elimina; si respondes `n`, se conserva.
* Es útil para eliminar archivos importantes con seguridad.

## Laboratorio 4

```bash
mateo@equipo:~$ mkdir vacío
mateo@equipo:~$ rmdir vacío
mateo@equipo:~$ ls
mateo@equipo:~$
```

### Análisis

* `rmdir` elimina solo directorios vacíos.
* Si el directorio contiene archivos o subdirectorios, `rmdir` falla.
* Es útil para limpiar carpetas vacías sin afectar contenido.

## Laboratorio 5

```bash
mateo@equipo:~$ mkdir lleno
mateo@equipo:~$ touch lleno/archivo1.txt lleno/archivo2.txt
mateo@equipo:~$ rmdir lleno
rmdir: failed to remove 'lleno': Directory not empty
```

### Análisis

* `rmdir` no puede eliminar directorios que contienen archivos o subdirectorios.
* Para eliminar un directorio con contenido, se debe usar otro comando (como `rm -r`).
* Esto previene la eliminación accidental de datos importantes.

## Laboratorio 6

```bash
mateo@equipo:~$ mkdir proyecto
mateo@equipo:~$ touch proyecto/main.py proyecto/config.json
mateo@equipo:~$ rm -r proyecto
mateo@equipo:~$ ls
# El directorio 'proyecto' ya no aparece en la lista
```

### Análisis

* La opción `-r` permite eliminar directorios junto con todo su contenido (archivos y subdirectorios).
* Este comando debe usarse con precaución, ya que borra de forma irreversible.
* `rm -r` es la forma adecuada de eliminar directorios no vacíos.

## Laboratorio 7

```bash
mateo@equipo:~$ mkdir datos
mateo@equipo:~$ touch datos/registro.txt datos/backup.log
mateo@equipo:~$ rm -ri datos
rm: descend into directory 'datos'? y
rm: remove regular file 'datos/registro.txt'? y
rm: remove regular file 'datos/backup.log'? y
rm: remove directory 'datos'? y
mateo@equipo:~$ ls
# El directorio 'datos' ya no aparece en la lista
```

### Análisis

* La opción `-ri` combina la recursividad con la confirmación interactiva.
* Antes de eliminar cada archivo o directorio, el sistema pregunta para evitar borrados accidentales.
* Es útil cuando quieres eliminar directorios con precaución.

## Laboratorio 8

```bash
mateo@equipo:~$ mkdir temp
mateo@equipo:~$ touch temp/file1.txt temp/file2.txt
mateo@equipo:~$ rm -rf temp
mateo@equipo:~$ ls
```

### Análisis

* La opción `-f` fuerza la eliminación sin pedir confirmación, incluso si hay archivos protegidos.
* Combinado con `-r` permite borrar directorios no vacíos rápidamente.
* Útil para scripts o cuando se requiere eliminar sin interrupciones, pero con precaución para evitar borrar datos accidentalmente.

## Laboratorio 9

```bash
mateo@equipo:~$ mkdir -p proyecto/{src,docs,tests}
mateo@equipo:~$ touch proyecto/src/main.c proyecto/docs/manual.txt proyecto/tests/test1.py

mateo@equipo:~$ rm -r proyecto

mateo@equipo:~$ ls
```

### Análisis

* `rm -r` elimina directorios con todo su contenido, incluyendo subdirectorios y archivos.
* Es importante asegurarse de apuntar al directorio correcto para evitar pérdida accidental de datos.
* En estructuras profundas, esta opción facilita la limpieza completa.

## Laboratorio 10

```bash
mateo@equipo:~$ mkdir -p trabajo/{informes,temporal,archivos}
mateo@equipo:~$ touch trabajo/informes/reporte1.doc trabajo/temporal/notas.txt trabajo/archivos/datos.csv

mateo@equipo:~$ rm -r trabajo/temporal

mateo@equipo:~$ ls trabajo

mateo@equipo:~$ rm -r trabajo

mateo@equipo:~$ ls
```

### Análisis

* Se eliminó primero un subdirectorio específico (`temporal`) para luego eliminar el directorio padre completo.
* Permite eliminar selectivamente partes de una estructura antes de una limpieza total.
* Útil para manejar grandes proyectos donde solo ciertas partes requieren ser borradas.
