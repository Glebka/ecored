# EcoRed

ESPHome based project to remotely control and track status of my EcoFlow Delta 2.
The idea is to make a big red button that will turn ON / OFF the invertor of Delta 2 and track it's status.

## How it works

Firmware connects to the Ecoflow using ESPHome ble_client. To do so you need to know the EcoFlow's MAC address.
To check it use the [nRF Connect for Mobile](https://play.google.com/store/apps/details?id=no.nordicsemi.android.mcp&hl=en) app.
Just search for BT devices nearby.

When connected, EcoFlow starts sending status packages from several internal components. The firmware accepts only packets from EcoFlow invertor.
It is possible to add support for other components as well such as: BMS, EMS, MPPT (Solar charging), etc.

## How to build?

1. Create ``secrets.yaml`` at the root of the repo, use ``secrets_example.yaml`` as reference. Fill it with desired values.
1. Connect the board to PC and run the following command:

        esphome run ecored.yml


## Known issues

Tested on ESP32 C3 Super Mini board with EcoFlow Delta2 with extra battery.

* ESP32C3 is really hot during operation

## References

* https://github.com/vwt12eh8/hassio-ecoflow
* https://github.com/nielsole/ecoflow-bt-reverse-engineering
