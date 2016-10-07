# Silicon Labs Sensor PMOD

The Silicon Labs Sensor PMOD (see [8]) has two I2C sensors mounted on it, i.e. the Si1145 proximity and light sensor and
the Si7020 temperature and humidity sensor. The Si7020 has a testing feature, an internal heater element that can be
used to “raise” the measured temperature when it is turned on.  
When the PMOD is connected, the reference design reads both these sensors, but the Si7020 temperature and humidity
readings are not used because the HTS221 sensor on the cellular shield already provides temperature and humidity.

slika

##Si1145 proximity and light sensor

The Si1145 (see [10]) is a low-power, reflectance-based proximity and light sensor in a 2x2mm package that can provide:

* Proximity detection adjustable from under 1 cm to over 50 cm
* Ambient light lux measurements with an IR correction algorithm
* UV index sensor


The application code reads the relevant registers and scales them as required. For the proximity sensor, values can be
interpreted as follows:

* value < 22000 : Object Far
* 22000 ≤ value < 24000 : Object in Vicinity
* 24000 ≤ value < 30000 : Object Near
* value ≥ 30000 : Object Very Near

slika

##Si7020 temperature and humidity sensor

The Si7020 (see [9]) is a relative humidity (0–80% ± 4%) and temperature (-10 to 85 degrees Celsius) sensor in a 3x3mm
package.  
The application code reads the relevant registers and scales them as required.

slika

##Wiring up the SiLabs PMOD Sensor to the PMOD connector

Please note that the PMOD cannot be plugged directly into the PMOD connector, as the pinouts do not match. Four
signals have to be connected between the Cellular kit and the SiLabs PMOD. Silkscreen text on the top side of the PMOD
board identifies the signals. On the PMOD socket, J10 on the cellular shield, pin 1 is the pin closest to the antenna bulkhead
connectors.


| SIGNAL | J10 (SHIELD) | SILABS PMOD | COLOR IN THE IMAGE BELOW |
|:------:|:------------:|:-----------:|:------------------------:|
|   VCC  |     Pin6     |     Pin6    |            RED           |
|   GND  |     Pin5     |     Pin5    |           BLACK          |
|   SDA  |     Pin4     |     Pin4    |           Pin4           |
|   SCL  |     Pin3     |     Pin3    |          YELLOW          |

slika



