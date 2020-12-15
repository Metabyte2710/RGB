# OpenRGB's setting structure

## Device detectors

Stored under the ``Detectors`` Key

The Subkey is ``detectors`` with a list of each possible one that openRGB uses

To disable a specific detector find it in the list and replace ``true`` with ``false``. To re-enable you can do the reverse

## Debug Devices

Stored under the ``DebugDevices`` key

The Subkey is ``devices`` which is a list ( ``[]`` )

Each entry in the list is a ``type`` key

The possible keys are:

1. keyboard (Matrix zone and a linear zone)

2. dram (Linear zone and single zone)

3. gpu (Linear zone and single zone)

4. motherboard (Linear zone and single zone)

See below example

```json
"DebugDevices": {
    "devices": [
        {
            "type": "dram"
        }
    ]
}
```

## Dark theme

Stored under the ``Theme`` key

The Subkey is ``Theme``

The possible modes are

1. light

2. dark

3. auto

The structure is as follows

```json
"Theme": {
    "theme": "dark"
}
```

The theme setting is only applicable in windows as it defaults to your system theme on linux

## Minimizing on X (Close)

Stored under the ``Minimize`` key

The Subkey is ``min_on_x``

``true`` will make it minimize when you hit X

``false`` will completely close OpenRGB

The structure is;

```json
"Minimize": {
    "min_on_x": true
}
```

As a side note; You can Re-show OpenRGB by double clicking the tray icon

## Auto Updates

Stored under the ``Updates`` key

The Subkeys are;

* ``fork`` (CalcProgrammer1, Herosilas12, k1-801, etc)

* ``branch`` (Master, feature-devel, etc)

The structure is;

```json
"Updates": {
    "fork": "CalcProgrammer1",
    "branch": "master"
}
```

These ard **case sensitive**, I have coded auto updates in a way that it will let you know if you miss cased something but regrardless make sure you use the right casing
