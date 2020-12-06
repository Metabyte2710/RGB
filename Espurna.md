Espurna is an open source firmware for ESP8266-based lighting devices such as smart bulbs and smart switches.  It supports RGB control for devices which have RGB capability, and can be controlled via OpenRGB by adding your Espurna device information to the OpenRGB configuration file.

An example Espurna device configuration entry:

```
    "EspurnaDevices": {
        "devices": [
            {
                "apikey": "2E251541800B8C8B",
                "ip": "192.168.4.103",
                "port": "80"
            }
        ]
    },
```

* `apikey` - The Espurna device's API key, pulled from the Admin page in the Espurna web UI

* 'ip' - The Espurna device's IP address

* `port` - the network port of the Espurna API, usually port 80