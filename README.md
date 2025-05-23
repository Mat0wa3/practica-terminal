```bash
mateo@equipo:~$ touch prueba.txt
mateo@equipo:~$ ls
prueba.txt
```

# Lección 2
## Laboratorio 1
```bash
mateo@equipo:~$ pwd
/home/mateo
```

## Análisis de la Ruta:
La ruta /home/mateo se puede descomponer así:

/ : El directorio raíz del sistema.

home : Contiene los directorios personales de los usuarios.

mateo : Es el directorio personal del usuario Mateo. Aquí se encuentran mis archivos, configuraciones y demás documentos personales.

Esta ruta indica que actualmente se está trabajando dentro del directorio personal del usuario Mateo.

## Laboratorio 3

```bash
mateo@equipo:~$ cd /home
mateo@equipo:/home$ pwd
/home
mateo@equipo:/home$ cd mateo
mateo@equipo:/home/mateo$ pwd
/home/mateo
```

## Análisis:
Con cd /home, el usuario navega al directorio principal donde se almacenan los perfiles de usuario.

Con pwd, se confirma que efectivamente está en /home.

Finalmente, con cd mateo, el usuario accede a su propio directorio personal.