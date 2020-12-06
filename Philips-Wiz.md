Philips Wiz smart lights can be controlled by OpenRGB.  These bulbs must be set up and paired first using the official Wiz app, but after they are connected to your network you can add your Wiz lights to the OpenRGB configuration file.

An example Philips Wiz configuration entry:

```
    "PhilipsWizDevices": {
        "devices": [
            {
                "ip": "192.168.4.11"
            }
        ]
    }
```

* `ip` - IP address of Wiz light.  You can find this in your WiFi router's administration page.