# Cactus-WHID
## how to install version ESPloit V2.7.41 
I explain how to install the version ESPloit V2.7.41 either because the Cactus WHID has been configured wrong or because we want to update the version. 

## Preparación del IDE de arduino
1. Descargamos el IDE de arduino de la web oficial https://www.arduino.cc/en/software

2. Añadimos el enlace de las tarjetas adicionales en el IDE
   - Abrimos Arduino IDE
   - Vamos a Archivo/Preferencias y añadimos esta URL en "Gestor de URLs Adicionales de Tarjetas" http://arduino.esp8266.com/stable/package_esp8266com_index.json
   - Le damos a "OK" y cerramos la ventana

3. Instalamos la tarjeta ESP8266 en el IDE
   - Vamos a la pestaña Herramientas/Placa/Gestor de tarjetas y buscamos "esp8266"
   - Instalamos "esp8266 by ESP8266 community" version 2.3.0 y click en "cerrar"

4. Instalamos los recursos de Json en el IDE
   - Vamos a la pestaña Programa/Incluir Libreria y buscamos "ArduinoJson"
   - Instalamos "ArduinoJson by Benoit Blanchon" version 5.11.0 y click en "cerrar"

5. Biblioteca para la tarjeta ESP8266
   - Descargamos el zip: https://github.com/exploitagency/esp8266FTPServer/archive/feature/bbx10_speedup.zip
   - Vamos a la pestaña Programa/Incluir Libreria/Añadir Biblioteca .ZIP
   - Seleccionamos el ZIP que nos hemos descargado

6. Ya esta configurado y preparado el Arduino IDE


## Instalación del Software en el Cactus WHID
1. El software esta en la raiz de este github en la carpeta "ESPloitV2" pero se puede descargar en el github oficial: https://github.com/exploitagency/ESPloitV2/archive/master.zip

2. Cargar esp8266Programmer
   - Nos vamos a la carpeta flashing/esp8266Programmer y abrimos el archivo "esp8266Programmer.ino"
   - Vamos a la pestaña Herramientas/Placa y seleccionamos la placa "LilyPad Arduino USB"
   - Seleccionamos el puerto COM donde esta nuestro Cactus WHID
   - Por ultimo le damos a Subir programa
   
3. Compilar binarios ESP_Code
   - Nos vamos a la carpeta source/ESP_Code y abrimos el archivo "ESP_Code.ino"
   - Vamos a la pestaña Herramientas/Placa y seleccionamos la placa  "Generic ESP8266 Module"
   - Vamos a la pestaña Herramientas/Flash Size y seleccionamos  "4M (3M SPIFFS)"
   - Vamos a Herramientas y seleccionamos la opcion "Exportar binarios compilados"
   - De esta manera se nos ha tenido que generar un archivo .bin llamado "ESP_Code.ino.generic.bin"

4. Flashear el firmware en el chip ESP-12S
   - El software esta en la raiz de este github en la carpeta "nodemcu" pero se puede descargar en el github oficial: https://github.com/nodemcu/nodemcu-flasher
   - Ejecutamos el archivo "ESP8266Flasher.exe" guardado en la ruta nodemcu/Win64/Release
   - Una vez abierto nos vamos a la pestaña "Config" y añadimos la ruta del binario "ESP_Code.ino.generic.bin" que generamos anteriormente
   - Volvemos a la Pestaña "Operation", seleccionamos el Puerto COM donde esta nuestro Cactus WHID y le damos al boton "FLASH"
   - Una vez acabado ya estaria por finalizado este apartado
  
5. Cargar Arduino_32u4_code 
   - Volvemos a la carpeta "ESPloitV2/source" y abrimos el archivo "Arduino_32u4_Code.ino"
   - Una vez abierto nos vamos a Herramientas/Placa y seleccionamos la placa "LilyPad Arduino USB"
   - Seleccionamos el puerto COM donde esta nuestro Cactus WHID
   - Por ultimo le damos a Subir programa
   
6. Ya estaria nuestro Cactus WHID configurado y listo para usarse, recordar que el punto de acceso se llama "Exploit" y la contraseña es "DotAgency"

## Software y recursos usados
https://github.com/whid-injector/WHID/tree/master/ESPloitV2_whid

https://github.com/nodemcu/nodemcu-flasher

## Wiki Cactus WHID
https://github.com/whid-injector/WHID/wiki

