Some EVGA graphics cards have an RGB controller that enumerates on the GPU I2C bus at address 0x49.  This controller uses basic chip addressing and exposes registers for RGB control.  There are multiple generations of EVGA controller with different register layouts.

# EVGA RGB v1 (Pascal)

## Supported Cards

| PCI Vendor | PCI Device | PCI Sub-Vendor | PCI Sub-Device | Card Name                 |
| ---------- | ---------- | -------------- | -------------- | ------------------------- |
| 0x10DE     | 0x1B81     | 0x3842         | 0x6276         | EVGA GeForce GTX 1070 FTW |

## Registers

| Register Address | Description |
| ---------------- | ----------- |
| 0x09             | Red         |
| 0x0A             | Green       |
| 0x0B             | Blue        |
| 0x0C             | Mode        |

## Modes

| Mode Value | Description |
| ---------- | ----------- |
| 0x00       | Off         |
| 0x01       | Static      |
| 0x02       | Rainbow     |
| 0x05       | Breathing   |

# EVGA RGB v2 (Turing)

## Supported Cards

| PCI Vendor | PCI Device | PCI Sub-Vendor | PCI Sub-Device | Card Name                       |
| ---------- | ---------- | -------------- | -------------- | ------------------------------- |
| 0x10DE     | 0x1E87     | 0x3842         | 0x2182         | EVGA GeForce RTX 2080 XC GAMING |

## Registers

| Register Address | Description                |
| ---------------- | -------------------------- |
| 0x60             | Mode                       |
| 0x61             | Fixed 0x01                 |
| 0x62             | Breathing Speed LSB        |
| 0x63             | Breathing Speed MSB        |
| 0x64             | Breathing Speed LSB        |
| 0x65             | Breathing Speed MSB        |
| 0x66             | Color A Speed LSB          |
| 0x67             | Color A Speed MSB          |
| 0x68             | Color B Speed LSB          |
| 0x69             | Color B Speed MSB          |
| 0x6C             | Color A Red                |
| 0x6D             | Color A Green              |
| 0x6E             | Color A Blue               |
| 0x6F             | Color A Brightness (0-100) |
| 0x70             | Color B Red                |
| 0x71             | Color B Green              |
| 0x72             | Color B Blue               |
| 0x73             | Color B Brightness (0-100) |
| 0x74             | Speed LSB                  |
| 0x75             | Speed MSB                  |

## Modes

| Mode Value | Description | Inputs                  |
| ---------- | ----------- | ----------------------- |
| 0x00       | Off         | None                    |
| 0x01       | Static      | Color A                 |
| 0x22       | Breathing   | Color A, Color B, Speed |
|            | Pulse       | Color A, Color B, Speed |
| 0x0F       | Rainbow     | Color A Brightness      |

## Speeds

### Breathing

| Speed Value | Speed   |
| ----------- | ------- |
| 0xE204      | Minimum |
| 0xEE02      | Default |
| 0xFA00      | Maximum |

### Pulse

| Speed Value | Speed   |
| ----------- | ------- |
| 0xC409      | Minimum |
| 0xDC05      | Default |
| 0xF401      | Maximum |