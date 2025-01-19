# TVOC & eCO2 Sensor
A DIY TVOC &amp; eCO2 sensor for integration into Home Assistant using ESP-Home.

![TVOC sensor setup](https://github.com/user-attachments/assets/51dccefc-0315-4f6b-a482-2c2220a997dd)


## Project Outline
A DIY Total Volatile Organic Compounds (TVOC) and equivalent Carbon Dioxide (eCO2) sensor to measure the air quality within my room. This is particularly important due to the recent addition of a 3D printer within the space. I'd also like this sensor to be able to connect to my Home Assistant instance to be able to consolidate and manage it alongside existing smart home sensors.

## Components
- Seeed XIAO ESP32C3 board
- CCS811 HDC1080 eCO2 and TVOC sensor
- Custom PCB
- Blue LED
- 100 ohm resistor
- 3D Printed enclosure

## Prototype
Built using a breadboard. The ESP board communicates with Home Assistant via ESP-Home and controls power input and distribution. The TVOC/eCO2 sensor is wired up to the ESP board and reports the current TVOC and eCO2 values every 15 seconds. The Blue LED acts as a status light and flashes when the device is disconnected from the Home Assistant instance but can also be toggled manually from the Home Assistant dashboard.

![PXL_20240814_201309361 MP](https://github.com/user-attachments/assets/00fcb3ac-e160-42e1-b1a2-019843aa267a)

## Initial Enclosure Design
Initial enclosure designs focused on keeping the components separate without the use of a custom PCB due to my lack of experience with PCB design. All enclosure designs would be done in Autodesk Fusion 360 as it is one of the most widely used hard surface modelling packages that offers a free version for hobbyists. The first few versions featured a slot for the ESP board to be pressed into and held into place at the corners, a shelf for the CCS811 HDC1080 sensor board itself (to allow routing of cables underneath), and a friction fit mount for the LED. These components would then be covered with a slide-on lid and mounted to the wall using a dovetail wall plate. 

![TVOC sensor enclosure - V6](https://github.com/user-attachments/assets/45348d9e-54ed-4228-84a7-a2d02dbf3f06)

## PCB Design
Eventually I decided that it made a lot more sense to take the time to learn some PCB design in order to keep the sensor compact and improve the overall look. After some research I decided to use KiCad due to the large amount of online tutorials and it being free to use. The PCB design took roughly 2 days to finalise and was sent to PCBWay for manufacture.

![TVOC_sensor_schematic](https://github.com/user-attachments/assets/ce7ac6d2-326b-46af-bff7-269a6d8d90e3) 
![TVOC_sensor_PCB_Diagram](https://github.com/user-attachments/assets/77f2f9c0-3718-4ba9-b290-140e4088f1f1)
![TVOC sensor PCB v1](https://github.com/user-attachments/assets/f63fce53-3b3a-4baa-9f8b-fd73354df82f)

## PCB Enclosure Design
After changing to using a PCB to hold all of the components the sensor enclosure had to be altered as well. Luckily, this was not a long process as I only had to worry about holding the PCB in place rather than the individual components and so most of the difference between versions were just slight tolerance changes.

![TVOC sensor enclosure - V7-8-9](https://github.com/user-attachments/assets/dcffec94-d5b3-4f29-87ac-5a1a25d85e00)

## The Final Design
![TVOC sensor final](https://github.com/user-attachments/assets/06a5b8e1-006b-4739-9faa-08bfb45d22a0)
![TVOC sensor final (6)](https://github.com/user-attachments/assets/55d8d217-96f9-4ab1-8893-1945ef93c1b2)
![TVOC sensor setup](https://github.com/user-attachments/assets/f1a9a743-d505-4261-97ad-a7081b7c55d7)

## Conclusion
During this project I have learned a lot about PCB design and smart home integration using ESP-Home that I can carry over to future projects. However, I do have some regrets with this project:
- Low accuracy components - While the CCS811 HDC1080 sensor does provide some rough idea of air quality it doesn't come pre-calibrated and doesn't provide an accurate CO2 reading. I should have done more research into the types on sensors available and maybe spent a bit more for a higher quality sensor.
- Late switch to PCB - Deciding to use a custom PCB design earlier in the project could have cut the complexity of the enclosure and project length in half.
- No battery power - The Seeed XIAO ESP32C3 has a built in charging circuit that was not taken advantage of during this project.
