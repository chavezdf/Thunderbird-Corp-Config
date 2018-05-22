# Distribuir Thunderbird en un Ambiente Empresarial

Este proyecto intentará documentar el proceso de creación de un paquete de Thunderbird personalizado para PDVSA.

Referencias: 

* https://developer.mozilla.org/en-US/docs/MCD%2C_Mission_Control_Desktop_AKA_AutoConfig
* https://mike.kaply.com/2012/03/16/customizing-firefox-autoconfig-files/
* https://mike.kaply.com/2012/03/30/customizing-firefox-default-profiles/

## Requerimientos

* Instalador de **Mozilla Thunderbird** - https://ftp.mozilla.org/pub/thunderbird/releases/
* 7-zip - http://www.7-zip.org/a/7z1512.msi
* Crear una carpeta llamada **Thunderbird**, en su lugar favorito.
* Descargar nuestros fuentes - http://gilab.occ.pdvsa.com/PEOcc/Thunderbird-PDVSA-Config/repository/archive.zip?ref=master
* Descomprimir los fuentes y ubicarlos en el lugar de su preferencia.

## Pasos para aplicar una configuración personalizada

* Ubicar el instalador descargado en la carpeta **Thunderbird**
* Descomprimir el instalador de Thunderbird, utilizando **7zip** con un simple **"boton derecho->7zip->Extract to "Thunderbird Setup XX.X.X"**. 

_**Nota:** Deberá haberse creado una carpeta con el mismo nombre del instalador.  **Ejemplo:** Para el instalador **"Thunderbird Setup 52.3.0.exe"** debe descomprimirse en la carpeta **"Thunderbird Setup 52.3.0"**._

* Copiar los archivos de configuración de nuestros fuentes **"core"** en la carpeta recien descomprimida.

## Pasos para repaquetizar los cambios
* Dentro de la carpeta **Thunderbird XX.X.X**, seleccionar las carpetas **"core"**, **"win32"** y el archivo **"setup.exe"** y con el boton derecho del mouse seleccionar la acción **"7zip-->Añadir a "Thunderbird Setup XX.X.X.7z"**.
* El archivo resultante debe ser un archivo llamado **"Thunderbird Setup XX.X.X.7z"**
* Mover el archivo recien comprimido a la carpeta **"exec"** de nuestros fuentes.
* Editar el archivo crearPaquete.cmd y ajustar el número de version de thunderbird de ser necesario.
* Ejecutar el archivo **"crearPaquete.cmd"**. Este generará el ejecutable final: **"Thunderbird Setup XX.X.X-PDVSA.exe"**
