# HA-Openhasp-for-Shelly-TRV
openhasp plate to manage several shelly TRV thermostatic radiator valves in HomeAssistant

![My Image](screen.jpg)

## Description:
- Homeassistant installed on a raspberry PI
- Homeassistant configuration: Homeassistant 2023.4.2 Supervisor 2023.04.0 Operating System 9.5 Frontend 20230309.1 - latest 
- Used display is a Sunton ESP32-8048S070 (ESP32-S3) (see devices page on OpenHasp website).  Resolution 800*480.  For other resolutions, the pages.jsonl file (see below) will have to be adapted.
- The goal of this configuration is to have a thermostat arc slider and gauge to read the temperature and preset and to set a new temperature or change the preset.
- Next to the arc and gauge is a button matrix that allows to choose the room for which the temperature can be shown/adjusted.
- This setup uses shelly TRV thermostatic radiator valves, although other climate entities should also work with a minimal modification of the yaml file.


## pages.jsonl
In this case, using Openhasp on HomeAssistant is done by defining all graphical objects of the plate in the pages.jsonl file that is saved on the display board itself. 

## openhasp.yaml
Is where the connection is made between the entities of the Shelly TRV devices and the objects of the OpenHASP plate. To use it, copy the file in the same folder as configuration.yaml and add
```
openhasp: !include openhasp.yaml
```
in the configuration.yaml file to refer to it.

**sensor.thermroom**: This entity is a variable.  Install "variables+history" from HACS.  Once installed go to Settings-Devices and Services, add integration, look for variables+history, add a new sensor and name it "thermroom".  Once this is done, a new sensor "sensor.thermroom" is created.  The state of this sensor is the device name of the TRV you select on the Button Matrix on the OpenHasp screen. 

## ToDo
- Make it possible for multiple displays to use the same plate logic and avoid having to copy-paste the contents of openhasp.yaml for each plate/display (suggestions are welcome)
- Do the above in such a way that each plate has its own variable sensor.thermroom to avoid switching rooms on one plate to be reflected on the other plates.
- Autodetect all shelly TRV instead of listing them in the yaml file.
- Sensitivity and usability of the arc slider is poor.  I wonder if it can be improved.  For now, I do not use it often since I mainly switch between presets to adjust temperatures or use the short click on the gauge center to increase temperature and long click to decrease
 
