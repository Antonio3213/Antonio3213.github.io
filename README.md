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

##Practica 2.2 
Autor: Vasquez Pacheco Marco Antonio
Contacto: 
Fecha: 2023-10-16
Descripción: Desplegar temperatura en OLED Display con bitArray imagen

```python

import machine
import utime
from ssd1306 import SSD1306_I2C

sensor_temp = machine.ADC(4)

i2c = machine.I2C(0, scl=machine.Pin(21), sda=machine.Pin(20))
oled = SSD1306_I2C(128, 64, i2c)

def obtener_temperatura():
    lectura = sensor_temp.read_u16() * 3.3 / (65535)
    temperatura = 27 - (lectura - 0.706) / 0.001721
    return temperatura

def mostrar_imagen_temperatura(temperatura):
    if temperatura < 10:
        imagen = bytearray(b'\x00\x00\x00\x00\x00\x00\x00\x00')
    elif 10 <= temperatura < 30:
        imagen = bytearray(b'\xff\xff\xff\xff\xff\xff\xff\xff')
    else:
        imagen = bytearray(b'\x00\xff\x00\xff\x00\xff\x00\xff')
    oled.fill(0)
    oled.framebuf.blit_buffer(imagen, 0, 0, 8, 1)
    oled.show()

while True:
    temp = obtener_temperatura()
    print('Temperatura actual: {} °C'.format(temp))
    mostrar_imagen_temperatura(temp)
    utime.sleep(5)  ```
