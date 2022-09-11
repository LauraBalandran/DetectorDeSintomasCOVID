
# DetectorDeSintomasCOVID
Este repositorio contiene la aplicación para detectar lo síntomas de COVID por medio del sensor pulsoxímetro MAX30102 y sensor de temperatura infrarroja MLX90614.

## **Introducción**


La aplicación se visualiza en un flow de Node-red que recibe por mqtt los valores del circuito que tiene el sensor de temperatura MLX90614 y pulsoximetro MAX30102.

![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/Diagrama%20del%20circuto%20pulsoximetro-temperatura.png)


![Circuito de los sensores MLX90614 y MAX30102](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/circuito%20sensor%20MLX90614%20y%20MAX30102.jpg)

Valores recibidos en terminal Ubuntu con la subscripción al tema codigoIoT/detectorSintomas/flow
![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/valores%20por%20mqtt.png)

![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/nodo%20mqtt.png)


Posteriormente toma los valores para mostrarlos en las gráficas mostradas en el Dashboard, donde también se solicita los datos del paciente, los guarda en variables globales para luego enviarlos y almacenarlos en una BD de Mysql llamada “detectorsintomas” en una tabla llamada “registro”.
![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/DashboardDetectorSintomasCOVID.jpeg)


![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/datos%20en%20la%20BD.png)


Al oprimir un botón llamado “Realizar diagnostico”, una función compara los valores para emitir un proto diagnóstico emitido en audio y enviar este último valor por correo electrónico.
![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/nodo%20boton.png)

![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/correo%20recibido.png)

![enter image description here](https://github.com/LauraBalandran/DetectorDeSintomasCOVID/blob/main/Imagenes/ver%20correo.png)


En el programa de la IDE de arduino se realiza una conexión a internet por wifi, para enviar un json por mqtt al tema codigoIoT/detectorSintomas/flow
