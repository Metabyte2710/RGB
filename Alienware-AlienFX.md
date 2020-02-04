Alienware laptops provide an RGB control system called AlienFX.  This project has support for this RGB system:

https://github.com/bchretien/AlienFxLite

Looking through that code, it looks like the AlienFX system is a USB controller that enumerates at 187C:0512.  It uses USB control transfers with the following parameters:

```
#define SEND_REQUEST_TYPE 0x21
#define SEND_REQUEST 0x09
#define SEND_VALUE 0x202
#define SEND_INDEX 0x00

#define READ_REQUEST_TYPE 0xa1
#define READ_REQUEST 0x01
#define READ_VALUE 0x101
#define READ_INDEX 0x0
```

The AlienFX controller uses 4 bits per color channel.

# Commands

| Command Value | Command Description  |
| ------------- | -------------------- |
| 0x00          | End Storage Block    |
| 0x01          | Set Morph Color      |
| 0x02          | Set Blink Color      |
| 0x03          | Set Color            |
| 0x04          | Loop Block End       |
| 0x05          | Transmit and Execute |