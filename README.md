## Practicas Antonio : 

## Proyecto Utiliza el WiFi: envía mensajes a tu smartphone : 
Utiliza la aplicación Blynk para enviar mensajes a tu smartphone. Para ello, lo primero que tienes que hacer es conectar tu Raspberry Pi Pico con la WiFi. Esto funciona con un módulo WiFi externo alimentado por batería que puedes conectar a tu microcontrolador. A continuación, hay que configurar la aplicación Blynk, que conecta los microcontroladores y otros dispositivos IoT a través de Internet. También puede utilizarse para recibir mensajes.

## Materiales 
*Raspberry Pi Pico W
*Sensor o entrada de datos
*Conexión a Internet
*Acceso a Internet para la Raspberry Pi Pico W
*Fuente de energía
*Conocimientos de programación

##  Imagenes
![](https://industrysurfer.com/wp-content/uploads/2023/06/IoT-LED-Control-using-Blynk-2.0-Raspberry-Pi-Pico-W.png)

## El Sensor DHT11:

*Especificaciones básicas: El DHT11 es un sensor que puede medir la temperatura en un rango de 0°C a 50°C con una precisión de ±2°C y la humedad relativa en un rango de 20% a 80% con una precisión de ±5%. Estas lecturas se pueden obtener mediante la comunicación digital con la Raspberry Pi.

*Conexión: El DHT11 tiene tres pines: VCC (alimentación), DAT (datos) y GND (tierra). Para conectarlo a la Raspberry Pi, conecta VCC a un pin de 3.3V, DAT a un pin GPIO (por ejemplo, GPIO17), y GND a tierra (GND).

*Programación: Para leer los datos del sensor en la Raspberry Pi, necesitas escribir un programa en Python (o en otro lenguaje compatible) que configure el pin GPIO para recibir datos y luego lea los valores del sensor a través de ese pin. Puedes utilizar la biblioteca "Adafruit_DHT" para facilitar la lectura de datos..

![](https://lirc.com.mx/web/image/product.product/5605/image_1024/%5BLE029%5D%20Sensor%20de%20Temperatura%20y%20Humedad%20DHT11?unique=f8a5dd3)
