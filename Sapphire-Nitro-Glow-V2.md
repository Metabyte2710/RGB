Sapphire has three different versions of their Nitro Glow RGB system.  The second generation of Nitro Glow uses a single-zone I2C controller that enumerates at address 0x55.

# Supported Devices

    * 

# Registers

| Register Address | Register Description               |
| ---------------- | ---------------------------------- |
| 0x10             | Mode (see Modes)                   |
| 0x11             | Speed                              |
| 0x12             | Count                              |
| 0x13             | One Color Time                     |
| 0x15             | Rainbow Speed                      |
| 0x16             | Serial Speed                       |
| 0x1A             | Red                                |
| 0x1B             | Green                              |
| 0x1C             | Blue                               |
| 0x3E             | Brightness                         |

# Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x00       | Runway           |
| 0x01       | One Color        |
| 0x02       | Rainbow          |
| 0x03       | Serial           |
| 0x04       | Custom           |
| 0x05       | Off              |