# Forest Fire Sensor System
## Introduction
Forests are one of the most essential natural resources on Earth. In order to sustain life on Earth we must conserve these forests. In this project we will use an Arduino UNO, a flame detector, a flame detector, and a MQ-2 gas sensor. These devices can be installed at strategic locations all over the forest. The devices are placed with a water reservoir at that location in order to extinguish the fire in case of a fire. 

## Components and Supplies
 * Arduino UNO  - 1
 * Flame Sensor - 1
 * MQ-2 Gas Sensor  - 1
 * Buzzer - 1
 * Red LED  - 1

## Detecting the Fire

### Role of Flame Sensor
The sensors in the flame detector will sense the radiation that is sent by the flame, the sensor of the flame detector would be a photoelectric sensor and this sensor would convert the radiant intensity signal of the flame to a relevant voltage signal and this signal would be converted after that it would be processed in a single chip microcomputer and is converted as output. The high-speed response of these sensors can prove critical in case of a fire.

![image](https://user-images.githubusercontent.com/82715887/120279378-fb9a1800-c2d3-11eb-8e19-abbed31a709c.png)

The wavelengths corresponding to the peak emissions of the Sun (5777 K), the Earth's surface (300 K) and forest fires (600 to 1000 K).

### Role of MQ-2 Sensor
MQ-2 gas sensor has high sensitivity to propane and smoke, also can detect the natural gas and other flammable gases as well. In case of heavy smoke, the IR flame sensor may not be able to detect the flames. Additionally, smoke travels and spreads faster than heat. Therefore, we use the MQ-2 Sensor to detect smoke to detect forest fires at the earliest.

## Arduino Code

```

/*
Forest Fire Sensor- Detects the presence of a flame and the presence of smoke
*/

const int flameSensor = 11; //Defining the pin for the Flame Sensor
const int smokeSensor = A0; //Defining the pin for the MQ2 smoke sensor
const int buzzer = 5; //Defining the pin for the buzzer
const int led = 4; // Defining the pin for the LED
int thresholdSmoke = 175; //Threshold for sensing smoke
int Flame= HIGH; // Initial value of Flame

void setup()
{
  //Setup the functions of the various pins
  pinMode(buzzer,OUTPUT);
  pinMode(smokeSensor,INPUT);
  pinMode(led,OUTPUT);
  pinMode(flameSensor,INPUT);
  delay(500);  
}

void loop() 
{
  int smoke = analogRead(smokeSensor); //Read the value from the MQ-2 sensor
  Flame = digitalRead(flameSensor); //Read the value from the Flame Sensor

  if(smoke>thresholdSmoke || Flame=LOW) // If smoke value exceeds the threshold or if a flame is detected
  {
    //Buzzer needs to beep
    tone(buzzer, 2000); // Send 1KHz sound signal
    digitalWrite(led,HIGH); // Turns on the LED warning
  }
  else
  {
    //Buzzer needs to stop beeping
    noTone(buzzer);     // Stop sound
    digitalWrite(led,LOW); // Turns off the LED warning
  }
}
```

## Further Advancements
The following improvements can be made with this project:
1. The Sensor System can be powered with the help of solar cells, making it a sustainable project
2. A machine learning algorithm can be trained in order to predict areas of the forest that are frequently affected by forest wildfires and these systems can be installed at those places.
