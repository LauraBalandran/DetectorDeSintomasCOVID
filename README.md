# DetectorDeSintomasCOVID
Este repositorio contiene la aplicación para detectar lo síntomas de COVID por medio del sensor pulsoxímetro MAX30102 y sensor de temperatura infrarroja MLX90614.

**Introducción**
La aplicación se visualiza en un flow de Node-red que recibe por mqtt los valores del circuito que tiene el sensor de temperatura MLX90614 y pulsoximetro MAX30102.

![enter image description here](Escririo)





Realiza la lectura de 25 muestras del MAX30102 cada 4 segundos, posteriormente se conectará a MQTT para enviar datos
