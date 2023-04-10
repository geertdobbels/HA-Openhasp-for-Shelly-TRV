# HA-Openhasp-for-Shelly-TRV
openhasp plate to manage several shelly TRV thermostatic radiator valves in HomeAssistant

## Description:
- Homeassistant installed on a raspberry PI
- Homeassistant configuration: Homeassistant 2023.4.2 Supervisor 2023.04.0 Operating System 9.5 Frontend 20230309.1 - latest 
- Used display is a Sunton ESP32-8048S070 (ESP32-S3) (see devices page on OpenHasp website).  Resolution 800*480.  For other resolutions, the pages.jsonl file (see below) will have to be adapted.
- The goal of this configuration is to have a thermostat arc slider and gauge to read the temperature and preset and to set a new temperature or change the preset.
- Next to the arc and gauge is a button matrix that allows to choose the room for which the temperature can be shown/adjusted.
- This setup uses shelly TRV thermostatic radiator valves, although other climate entities should also work with a minimal modification of the yaml file.


## pages.jsonl
In this case, using Openhasp on HomeAssistant is done by defining all graphical objects of the plate in the pages.jsonl file that is saved on the display board itself. 

## ToDo
- Make it possible for multiple displays to use the same plate logic and avoid having to copy-paste the contents of openhasp.yaml for each plate/display
- Do the above in such a way that each plate has its own variable sensor.thermroom to avoid switching rooms on one plate to be reflected on the other plates.
 
