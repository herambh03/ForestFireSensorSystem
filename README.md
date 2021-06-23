# Forest Fire Sensor System
## Introduction
Forests are essential natural resources on Earth. To sustain life on Earth, we must conserve these forests. This project will use an Arduino UNO, a flame detector, a flame detector, and an MQ-2 gas sensor. These devices can be installed at strategic locations all over the forest along with a water reservoir at that location to extinguish in case of a fire.

![image](https://user-images.githubusercontent.com/82715887/121134279-d9af1100-c850-11eb-9e2a-836963d7fbd2.png)

## Components and Supplies
 * Arduino UNO R3 - 1
 
 
 ![image](https://user-images.githubusercontent.com/82715887/121132908-5a6d0d80-c84f-11eb-8ffa-d429d5bbb460.png)
 * Flame Sensor - 1
 
 
 ![image](https://user-images.githubusercontent.com/82715887/121132966-6953c000-c84f-11eb-9452-2029f6443f4f.png)
 * MQ-2 Gas Sensor  - 1
 
 
 ![image](https://user-images.githubusercontent.com/82715887/121133183-aa4bd480-c84f-11eb-8010-c4f84afb7ac5.png)
 * Piezo Buzzer - 1
 
 
 ![image](https://user-images.githubusercontent.com/82715887/121133252-c0599500-c84f-11eb-8f13-596119b76bf0.png)
 * Red LED  - 1
 
 
 ![image](https://user-images.githubusercontent.com/82715887/121133333-d36c6500-c84f-11eb-8c55-fb3c0ce80d12.png)
* Resistors  - 3


![image](https://user-images.githubusercontent.com/82715887/121133525-1595a680-c850-11eb-8a56-025e0daf54fa.png)


## Detecting the Fire

### Role of Flame Sensor
The sensors in the flame detector will sense the radiation emitted by the flame, the sensor of the flame detector would be a photoelectric sensor. This sensor would convert the radiant intensity signal of the flame to a relevant voltage signal. This would then be processed in a single chip microcomputer and converted as output. Therefore, the high-speed response of these sensors can prove critical in case of a fire.
![image](https://user-images.githubusercontent.com/82715887/120279378-fb9a1800-c2d3-11eb-8e19-abbed31a709c.png)

The wavelengths corresponding to the peak emissions of the Sun (5777 K), the Earth's surface (300 K) and forest fires (600 to 1000 K).

### Role of MQ-2 Sensor
MQ-2 gas sensor has a high sensitivity to propane and smoke. It can detect natural gas and other flammable gases as well. In case of heavy smoke, the IR flame sensor may not be able to detect the flames. Additionally, smoke travels and spreads faster than heat. Therefore, we use the MQ-2 Sensor to detect smoke to detect forest fires at the earliest.

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

  if(smoke>thresholdSmoke || Flame==LOW) // If smoke value exceeds the threshold or if a flame is detected
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
## Simulate Model
https://www.tinkercad.com/things/8bv7PSLWi2L-forestfiresensorsystemfinal

## Further Advancements
The following improvements can be made with this project:
1. The Sensor System can be powered with the help of solar cells, making it a sustainable project.
2. A machine learning algorithm can be trained in order to predict areas of the forest that are frequently affected by forest wildfires and these systems can be installed at those places.
