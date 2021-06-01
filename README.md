# Forest Fire Sensor System
## Introduction
Forests are one of the most essential natural resources on Earth. In order to sustain life on Earth we must conserve these forests. In this project we will use an Arduino UNO, a flame detector, a flame detector, a temperature and humidity sensor and a MQ-2 gas sensor. These devices can be installed at strategic locations all over the forest. The devices are placed with a water reservoir at that location in order to extinguish the fire in case of a fire. 

## Components and Supplies
 * Arduino UNO  - 1
 * Flame Sensor - 1
 * DHT11 Temperature and Humidity Sensor  - 1
 * MQ-2 Gas Sensor  - 1
 * Buzzer - 1
 * Red LED  - 1

## Detecting the Fire

### Role of Flame Sensor
The sensors in the flame detector will sense the radiation that is sent by the flame, the sensor of the flame detector would be a photoelectric sensor and this sensor would convert the radiant intensity signal of the flame to a relevant voltage signal and this signal would be converted after that it would be processed in a single chip microcomputer and is converted as output. The high-speed response of these sensors can prove critical in case of a fire.

![image](https://user-images.githubusercontent.com/82715887/120279378-fb9a1800-c2d3-11eb-8e19-abbed31a709c.png)

The wavelengths corresponding to the peak emissions of the Sun (5777 K), the Earth's surface (300 K) and forest fires (600 to 1000 K).

### Role of Temperature Sensor
The DHT11 is a basic, low-cost digital temperature and humidity sensor. It uses a capacitive humidity sensor and a thermistor to measure the surrounding air, and spits out a digital signal on the data pin. 743K (470 *C) corresponds to the temperature of a fire. Hence, if the temperature measured exceeds this threshold value, the presence of a fire is detected. 

### Role of MQ-2 Sensor
MQ-2 gas sensor has high sensitivity to propane and smoke, also can detect the natural gas and other flammable gases as well. In case of heavy smoke, the IR flame sensor may not be able to detect the flames. Additionally, smoke travels and spreads faster than heat. Therefore, we use the MQ-2 Sensor to detect smoke to detect forest fires at the earliest.
