# OpenSmartCountry
Open Smart Country - Campo Inteligente Abierto
http://opensmartcountry.com/

## SIM800L
Para el envío de datos desde el campo será necesario establecer una comunicación móvil, no habrá WiFi, para ello lo más barao que he encontrado es el módulo SIM800L y de momento lo he constado con el Arduino UNO
### Hardware necesario:
* Arduino UNO
* Batería de 3.7 a 4.2 V, de momento estoy utilizando una de un móvil viejo
* Módulo SIM800L 
* Protoboard y algunos cables
* Una tarjeta SIM, estoy utilizando una 4G de Pepephone y de momento funciona perfectamente
* Soldador y estaño, la SIM800L me llegó sin los pines ni la antena soldados, además para la corriente de la batería tambien he soldado los cables para evitar problemas

### Entorno
Ide de Arduino

### Configuración
En el código de ejemplo BasicSIM800L.ino está descrito el esquema que he usado, es muy simple

### Referencias interesantes
Están también en el código pero de momento simplemente uso:
* SoftwareSerial.h de Arduino: https://www.arduino.cc/en/Reference/SoftwareSerial
* Guía de comandos AT de la página del chip: http://simcomm2m.com/UploadFile/TechnicalFile/SIM800%20Series_AT%20Command%20Manual_V1.09.pdf Es necesario estar registrado para descargarla pero no hay ningún requisito más


## openSmartCountrySensor
El proyecto consiste en dos sensores que envían los valores de temperatura y nivel de luz mediante MQTT a AWS IoT, una regla hace que los valores que se envían se guarden en una tabla en una base de datos DynamoBD

### Hardware necesario:
* Arduino Yun
* Sensor de temperatura TMP36
* Fotoresistencia
* Resistencia de 10 kiloohmnios
* Protoboard
* Cables de puente
 
### Entorno
* IDE Arduino: Fundamental, no instalarlo, descomprimirlo
* MQTT.fx para las pruebas
* Cuenta en AWS

### Configuración
* Para configurar la placa Arduino Yun https://www.arduino.cc/en/Guide/ArduinoYun
* Para los esquemas de los sensores se pueden ver los ejemplos 3 y 4 del Libro de Proyectos Arduino
* Para el entorno en AWS seguir la guia http://docs.aws.amazon.com/es_es/iot/latest/developerguide/what-is-aws-iot.html
* Para el SDK de AWS IoT para Arduino seguir la guia https://github.com/aws/aws-iot-device-sdk-arduino-yun