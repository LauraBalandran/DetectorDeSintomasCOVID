
# DetectorDeSintomasCOVID
Este repositorio contiene la aplicación para detectar lo síntomas de COVID por medio del sensor pulsioxímetro MAX30102 y sensor de temperatura infrarroja MLX90614.

## **Introducción**


La aplicación se visualiza en un flow de Node-red que recibe por mqtt los valores del circuito que tiene el sensor de temperatura MLX90614 y pulsioxímetro MAX30102, tomando la temperatura, oxigenación y ritmo cardíaco para algún paciente, luego registrarlo en una base de datos de MySQL junto con el proto diagnóstico realizado que será enviado por correo.

**

## Requerimientos

**

 - Ubuntu 20.04
 -  Instalar MySQL en Ubuntu 
 - Node-Red con mysql y email
 -  IDE de Arduino
 - Mosquito MQTT Broker instalado
 
 **

## Para el circuito

 - Módulo ESP32CAM
 - conversor serial-USB, FTDI232RL
 - pulsioxímetro MAX30102
 - sensor de temperatura MLX90614


**



**

## Descripción de la Aplicación

**

![Diagrama del CI](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/Diagrama%20del%20circuto%20pulsoximetro-temperatura.png)


![Circuito de los sensores MLX90614 y MAX30102](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/circuito%20sensor%20MLX90614%20y%20MAX30102.jpg)

Valores recibidos en terminal Ubuntu con la subscripción al tema codigoIoT/detectorSintomas/flow

![valores por mqtt en la terminal de ubuntu](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/valores%20por%20mqtt.png)

![nodo mqtt de Node-red](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/nodo%20mqtt.png)


Posteriormente toma los valores para mostrarlos en las gráficas mostradas en el Dashboard, donde también se solicita los datos del paciente, los guarda en variables globales para luego enviarlos y almacenarlos en una BD de Mysql llamada “detectorsintomas” en una tabla llamada “registro”.
![Dashboard de la aplicación](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/DashboardDetectorSintomasCOVID.jpeg)


![Datos almacenados en la BD](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/datos%20en%20la%20BD.png)


Al oprimir un botón llamado “Realizar diagnostico”, una función compara los valores para emitir un proto diagnóstico emitido en audio y enviar este último valor por correo electrónico.

![correo recibido](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/nodo%20boton.png)

![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/correo%20recibido.png)

![Abrir correo con el proto diagnóstico](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/ver%20correo.png)


En el programa de la IDE de arduino  realiza una conexión a internet por wifi, para enviar un json por mqtt al tema codigoIoT/detectorSintomas/flow
[Programa que realiza que recibe los valores de los sensores mencionados](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/tree/main/ESP32CAM/ESP32CAM-JSON-MQTT-MLX90614-MAX30102)

**

## Vistas previas y vídeos de los resultados

**

Vista Youtube 
