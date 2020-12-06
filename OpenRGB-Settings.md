# OpenRGB Setting

OpenRGB's configuration file is called OpenRGB.json and exists in the OpenRGB configuration directory.  The configuration directory depends on your OS:

* Windows: %APPDATA%\OpenRGB\

* Linux: ~/.config/OpenRGB/

The configuration directory also contains profile files (.orp) and saved size configuration files (.ors).

## OpenRGB JSON Configuration

The OpenRGB.json file contains several top-level JSON keys.  The keys are listed below along with the settings they contain.

### `Detectors` - Enable/Disable Devices
* `detectors` - List of booleans.  Values are `true` or `false`.  
  * To disable a specific detector find it in the list and replace `true` with `false`.  To re-enable you can do the reverse.
* `hid_safe_mode` - Boolean.
  * When set to `true`, this setting uses a slightly slower detection scheme for USB HID devices that works around a rare condition where the HID detection can crash the application.

### `DebugDevices` - Configure Debug Devices
* `devices` - List of device configurations containing the following keys:
  * `type` - String, one of "keyboard", "dram", "gpu", "motherboard", or "argb"

The types are defined as follows
1. `keyboard`: (Matrix zone and a linear zone)
2. `dram`: (Linear zone and single zone)
3. `gpu`: (Linear zone and single zone)
4. `motherboard`: (Linear zone and single zone)
5. `argb`: (Resizable linear zone)

See below example:
```json
"DebugDevices": {
    "devices": [
        {
            "type": "dram"
        }
    ]
}
```

### `Theme` (Windows only)
* `theme` - String, one of "auto", "light", or "dark"

Example:
```json
"Theme": {
    "theme": "dark"
}
```

### `E131Devices` - E1.31 Device Configuration
* `devices` - List of device definitions.  See [E1.31 wiki page](E1.31) for details.