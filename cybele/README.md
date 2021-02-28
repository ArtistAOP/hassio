# Cybele

## About

Integration of original [Cybele project](https://github.com/Hypfer/Cybele) to Home Assistant's Hass.io.
**Cybele** is BLE to MQTT Gateway for Smarthome and IoT Devices.

Tested configurations:
- Raspberry Pi 4B

Tested devices:
- Xiaomi Mi Smart Kettle YM-K1501

## Installation

First of all study [base instruction](../README.md).

In simple case:
- Create file \<config-folder\>/cybele.json like example below
- Replace _my_user_ and _my_password_ with your credential to MQTT broker.
- Add your devices.

Example of configuration:
```
{
    "mqtt": {
        "url": "mqtt://my_user:my_password@core-mosquitto"
    },
    "dongles": [
        {
            "hciDevice": "hci0",
            "mode": "le",
            "services": [],
            "devices": [
                {
                    "type": "MiKettleDevice",
                    "friendlyName": "Mi Kettle",
                    "mac": "B8:7C:6F:7C:0A:31",
                    "productId": 275
                }
            ]
        }
    ]
}
```

The configuration is the same to [the original configuration file](https://github.com/Hypfer/Cybele/blob/master/config.default.json).
For more information read the [Cybele instruction](https://github.com/Hypfer/Cybele/blob/master/Readme.md).