# ESP32-TC74 sample application

This example shows you how to use this library, to interface a TC74 Microchip temperature sensor with an ESP32 using it's I2C port.
- You can find TC74's datasheet in the following link : https://www.radiolocman.com/rs.php?u=https%3A%2F%2Fwww.rlocman.ru%2Fi%2FFile%2F2018%2F01%2F17%2FTC74.pdf
- Between changing modes (normal,standby) you need to wait some ms (tested with 250ms between changing modes) before making a reading.
- The accuracy of the sensor is ± 2 celcius.
- In the standby mode, the sensor keeps the last temperature value read before entering standby and the ADC is not active.
- If you only want the library and not the whole application you can copy tc74.c/h files to your project directory.

## Cabling

This is for ESP32 WROVER B series.
- GND   -> GND
- VDD   -> 3.3v
- SDA   ->  GPIO_NUM_21
- SCLK  ->  GPIO_NUM_22

### Hardware Required

This example can be executed on any ESP32 board. For this example i am using an ESP32 WROVER-B board. You can use this library for any ESP32 board by changing the GPIO pins for the I2C port accordingly.
You also need a TC74A53.3 Microchip's temperature sensor and some jumper wires.

### Configure the project

* When using Make build system, set `Default serial port` under `Serial flasher config`.

### Build and Flash

Build the project and flash it to the board, then run monitor tool to view serial output:

```
idf.py -p PORT flash monitor (CMAKE configuration)
or
make flash monitor (MAKEFILE configuration)
```

(To exit the serial monitor, type ``Ctrl-]``.)

See the Getting Started Guide for full steps to configure and use ESP-IDF to build projects.

## Example Output

```
I (8010) TC74: Temperature is : 24
I (16010) TC74: Temperature is : 23
I (24010) TC74: Temperature is : 23
I (32010) TC74: Temperature is : 24
etc ...
```
