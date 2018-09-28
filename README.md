# Homebridge-Yamaha
homebridge-plugin for Yamaha AVR control with Apple-Homekit.

# Installation
Follow the instruction in [NPM](https://www.npmjs.com/package/homebridge) for the homebridge server installation. The plugin is published through [NPM](https://www.npmjs.com/package/homebridge-yamaha) and should be installed "globally" by typing:

    sudo npm install -g homebridge-yamaha

#Configuration

config.json

"manual_addresses" only needed if Bonjour/Autodetection doesn't work.

The inputs array describes the list of services to appear in homekit for each receiver.

Example:

  ```json
  {
    "bridge": {
        "name": "Homebridge",
        "username": "CC:22:3D:E3:CE:51",
        "port": 51826,
        "pin": "031-45-154"
    },
    "description": "This is an example configuration file for homebridge plugin for yamaha AVR",
    "hint": "Always paste into jsonlint.com validation page before starting your homebridge, saves a lot of frustration",
    "platforms": [
        {
            "platform": "YamahaAVR",
            "manual_addresses": {
                "Yamaha": "192.168.1.115"
            },
            "inputs": [
                {
                "play_volume": -56,
                "setInputTo": "Spotify",
                "zone": "Main_Zone",
                "display_name": "Spotify"
                },
                {
                "play_volume": -30,
                "setSceneTo": "0",
                "zone": "Main_Zone",
                "display_name": "Movie"
                },
                {
                "play_volume": -45,
                "setInputTo": "Spotify",
                "zone": "Zone_2",
                "display_name": "Outside music"
                }
            ]
        }
    ],
    "accessories": [
        {},
        {}
    ]
    }
