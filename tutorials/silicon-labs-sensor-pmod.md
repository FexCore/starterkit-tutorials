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

##Reference documents

Please follow the hyperlinks below to open the relevant reference documents. At the time of the writing of
this document these links were active but in time some content could move or change.

1. Avnet’s  [AT&T Cellular IoT Kit Getting Started Guide](http://cloudconnectkits.org/product/att-cellular-iot-starter-kit "cloudconnectkits.org/product/att-cellular-iot-starter-kit")
2. NXP’s [FRDM-K64F development platform](https://developer.mbed.org/platforms/FRDM-K64F/ "developer.mbed.org/platforms/FRDM-K64F/")
3. NXP’s [FXOS8700CQ 6-axis sensor with integrated linear accelerometer and magnetometer](http://www.nxp.com/files/sensors/doc/data_sheet/FXOS8700CQ.pdf "www.nxp.com/files/sensors/doc/data_sheet/FXOS8700CQ.pdf")
4. STMicroelectronics [HTS221 Capacitive digital sensor for relative humidity and temperature](http://www.st.com/content/ccc/resource/technical/document/datasheet/4d/9a/9c/ad/25/07/42/34/DM00116291.pdf/files/DM00116291.pdf/jcr:content/translations/en.DM00116291.pdf "www.st.com/content/ccc/resource/technical/document/datasheet/4d/9a/9c/ad/25/07/42/34/DM00116291.pdf/files/DM00116291.pdf/jcr:content/translations/en.DM00116291.pdf")
5. Seeed Studio’s [Xadow GPS module v2](http://www.seeedstudio.com/depot/Xadow-GPS-v2-p-2557.html "www.seeedstudio.com/depot/Xadow-GPS-v2-p-2557.html")
6. Quectel’s [L70-R GPS Specification](http://www.quectel.com/UploadFile/Product/Quectel_L70-R_GPS_Specification_V2.1.pdf "www.quectel.com/UploadFile/Product/Quectel_L70-R_GPS_Specification_V2.1.pdf")
7. NXP’s [Kinetis KL02 microcontroller](http://www.nxp.com/files/32bit/doc/data_sheet/KL02P20M48SF0.pdf?fasp=1&WT_TYPE=Data%20Sheets&WT_VENDOR=FREESCALE&WT_FILE_FORMAT=pdf&WT_ASSET=Documentation&fileExt=.pdf "www.nxp.com/files/32bit/doc/data_sheet/KL02P20M48SF0.pdf?fasp=1&WT_TYPE=Data%20Sheets&WT_VENDOR=FREESCALE&WT_FILE_FORMAT=pdf&WT_ASSET=Documentation&fileExt=.pdf")
8. Silicon Labs [Sensor PMOD](http://pages.silabs.com/rs/silabs/images/Sensor-PMD-DataSheet.pdf "pages.silabs.com/rs/silabs/images/Sensor-PMD-DataSheet.pdf")
9. Silicon Labs [Si7020 Humidity and Temperature Sensor](https://www.silabs.com/Support%20Documents%2FTechnicalDocs%2FSi7020-A20.pdf "www.silabs.com/Support%20Documents%2FTechnicalDocs%2FSi7020-A20.pdf")
10. Silicon Labs [Si1145 Proximity, UV and Ambient Light Sensor](https://www.silabs.com/Support%20Documents/TechnicalDocs/Si1145-46-47.pdf "www.silabs.com/Support%20Documents/TechnicalDocs/Si1145-46-47.pdf")


