# ESPHome-DeskPi-Fan-Controller
The ESPHome-DeskPi-Fan-Controller was built gor a very specific purpose. To limit the noise while keeping the DeskPi rack cooled to a set temperature. 

My minilab is located in the bedroom and tucked away in such a way that I need good airflow at the lowest possible noise. To achive this i decided to use ESPHome to control a few 5V fans which can be mounted in the vented blanks available. 

Development board
![IMG_7295](https://github.com/user-attachments/assets/0ca07002-0c42-4166-985e-d9d07aa3fba1)
![IMG_7277](https://github.com/user-attachments/assets/1ec7fca3-e15f-430d-a238-7eb99be5dabf)
Fully integrated board
![IMG_7376](https://github.com/user-attachments/assets/cc6a8f35-ffdc-4883-8e3f-03e2dc68ab2c)
![IMG_7380](https://github.com/user-attachments/assets/9bdae597-87ab-4e1c-9bfe-a7e993d10599)
![IMG_7382](https://github.com/user-attachments/assets/2b50afc4-b34d-43c6-9dd8-0e82427896df)


The schematics and ESPHome configuration is derived from https://github.com/patrickcollins12/esphome-fan-controller and the only original work is the PCB layout to fit the specific envelope in the vented blank. 

This repository contains
* The KiCad schematics
* The KiCad PCB layout
* The ESPHome yaml files for manual control via either ESPHome webserver interface or Home Assistant
* The ESPHome yaml files for PID control using a BME280 sensor either via breakout board OR directly onboard.

Board features
* The controller should take most ESP32-S3 devkits with standard pin-out but the board I used for the project is from DIYMORE.
* The controller fits neatly either between the two fans (require USB-C break out board) or on the side of two fans.
* New design with fully integrated ESP32, temperature sensor which fits in 40x40mm envelope. 

![Diymore-esp32-s3-pinout](https://github.com/user-attachments/assets/07f82ef4-fe70-4613-b51e-139530f3ae08)



