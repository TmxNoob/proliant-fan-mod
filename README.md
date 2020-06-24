# proliant-fan-mod

All resources to quiet down your proliant :)
Sorry for messy pinouts, dont have time now to draw images, will do soon though :)

## Repositories:
https://github.com/TmxNoob/proliant-arduino-code - arduino project

https://github.com/TmxNoob/proliant-fan-controller - Python controller

https://github.com/TmxNoob/proliant-fan-pcb - PCB files


## Pinouts:

### DL380P G8
| row with notch | row without notch |
| --- | --- |
| +12V | FAN_DETECT |
| NC | GND |
| PWM | FAN_ROTATION_DETECT |

This server has a weird issue where even though the server is off fan 6 receives 8-9V and since arduino shuts off the fan gets no PWM and goes to full speed.
Easiest fix is to apply power from fans +12v pin to arduino VIN pin so arduino stays on with the fan and sets its speed to 15% or whatever is default. In future arduino code I could see if I could detect this condition and make it fully stop the fan.

### DL380E G8 & DL360E G8
| row with notch | row without notch |
| --- | --- |
| GND | FAN_ROTATION_DETECT |
| PWM | FAN_DETECT |
| +12V | NC |
