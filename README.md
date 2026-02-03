# ESPHome-Fan-Controller
The ESPHome-Fan-Controller was built gor a very specific purpose. To limit the noise while keeping the DeskPi rack cooled to a set temperature. 

My minilab is located in the bedroom and tucked away in such a way that I need good airflow at the lowest possible noise. To achive this i decided to use ESPHome to control a few 5V fans which can be mounted in the vented blanks available.

<img width="300" alt="BoardDesign" src="https://github.com/user-attachments/assets/3a67f89c-1c93-4f16-a123-a45917998935" />
<img width="300" alt="3D-view" src="https://github.com/user-attachments/assets/f69d2a2b-3732-41fd-8983-040696939b19"/>
<img width="300" alt="picture" src="https://github.com/user-attachments/assets/4787273e-3b4c-4b94-b728-d3111aed9231"/>
<img width="300" alt="picture2" src="https://github.com/user-attachments/assets/c56e6a75-d4bd-41f1-ad71-1fdb7cd6aabc"/>
<img width="600" alt="picture3" src="https://github.com/user-attachments/assets/8f903b19-69e6-41e6-8726-531ee2365934"/>


The schematics and ESPHome configuration is derived from https://github.com/patrickcollins12/esphome-fan-controller and the only original work is the PCB layout to fit the specific envelope in the vented blank. 

### This repository contains
* The KiCad schematics
* The KiCad PCB layout
* The KiCad Project file
* BOM and CPL for production at JLCPCB
* The ESPHome yaml files for manual control via either ESPHome webserver interface or Home Assistant
* The automation for Home Assistant to change fan speed based on Server CPU temp using Glances integration

### Board features
* The controller is based on the ESP32-S3-MINI-1-N4R2
* The controller fits neatly in a 40mm fan slot (32x32mm M3 screw holes) and features a vertical USB-C connector for programming and power. 

# Prepare the yaml
Change the friendly name to your liking and set the wifi-ssid and password.

# Programming
1. Install ESPHome and build (Install) the yaml file.
2. Choose plug into computer option.
3. Plug the controller into your computer and hold down the boot button WHILE selecting the Jtag in the pop-up window.
4. Wait for the firmware to install

If ESPhome returns an error before installing the firmware, try to hold the boot button WHILE plugging it into the computer. I'm not sure what order is required - Maybe see the documentation.

Check that the installation works by going to the name you choose .local
<img width="600"  alt="esphomelocal" src="https://github.com/user-attachments/assets/74d72203-e1fd-48c5-b2b4-6de7ed6116ee" />

# Home Assistant
Install the ESPHome integration in Home Assistant.
Add a device and point to the local address of the Fan controller OR the IP-address.

I have 4 automations controlling the fans:
1. Setting the base speed at 7am to 60% (it gets warmer in the day)
2. Setting the base speed at 7.30pm to 30% (lower the noise in the night)
3. Set HIGH speed if the temperature goes above a certain temperature (See High-speed.yaml)
4. Set LOW speed if the temperature goes down again (See Low-speed.yaml)



