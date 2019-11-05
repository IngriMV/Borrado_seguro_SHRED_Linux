# Borrado seguro con la herramienta SHRED de Linux 

Muchas veces realizamos la eliminación de un archivo de una USB o de nuestra propia máquina, paso siguiente vacear papelera de reciclaje. **¿Qué pensaría si le afirmarán que esto no es suficiente?**...muchas veces perdemos nuestros dispositivos de almacenamiento portables, por cosas del destino algun mal intensionado las encuentra y con herramientas forenses adecuadas puede  rescatar la información que pensabamos que habíamos eliminado y la clasificamos como **privada**.

Alguna de las herramientas forenses más conocidas son:

-**Linux**
- Testdisk
- ddrescue
- Autopsy
- Foremost
- scalpel
- PhotoRec

-**Windows** 
- Autopsy
- OsForensics
- Data Recovery System(DRS)
- DFF
 
 Para más información el *portal del Instituto Nacional de Estándares y Tecnología (NIST, por sus siglas en inglés)* de los Estados Unidos que cuenta con un catalogo de herramientas necesarias para análisis Forense [NIST](https://toolcatalog.nist.gov/search/index.php?all_tools=all&ff_id=17&1%5B%5D=1) segun su necesidad.
 
 
 
 Muchas veces prestamos nuestros dispositivos USB si no quieres que alguien mal intencionado encuentre información no deseada el sistyema operativo **Linux** cuenta con la herramienta **SHRED** y hace parte del paquete coreutils. sobrescribir un archivo para ocultar su contenido y, opcionalmente, eliminarlo.
 
Abrimos una terminal y ejecutamos el comando

```
$ shred --help
```
Las opciones que tenemos:

-  **f:** force. cambia los permisos del archivo si fuera necesario
- **n:** número de veces a sobrescribir el archivo o partición (3 veces por defecto). Cuanto mayor sea este número, más difícil será su recuperación...Se recomienda 30 como minimo.
- **u:** trunca y elimina el archivo después de sobrescribirlo
- **v:** verbose o verborragico, muestra el progreso en pantalla
- **z:** zero, sobreescribe 0 para evitar dejar rastro.

## Para borrar un archivo de modo seguro podemos ejecutar el siguiente comando 
```
$ shred -n30 -uvz archivo.txt
```

## Para un dispositivo USB ejecutamos en la terminal el siguiente comando 

```
$ sudo fdisk -l
```
Una vez ubicado el dispositivo en este **Ejemplo** es **/dev/sdb1/**

```
$sudo shred -vu -n30 /dev/sdb1
```
 









