[[_TOC_]]

# What are they

The USB specification defines that all USB devices have a unique Vendor Identification and Product Identification. These are normally represented as a 4 digit hexidecimal number allowing for 65535 Vendors and 65535 Products for each vendor.

# How to find them

The unique device VID:PID combination can be found a number of ways. The easiest being from the terminal or powershell depending on your platform.

## Linux

1. Open your favourite terminal or login to the CLI
1. type `lsusb`
1. Find the device in question in the list

![image](uploads/000ccbcb370a5b82f361ec6222df737b/image.png)

## Windows

1. Run Powershell by hitting window key + R
1. Type `powershell` in the run dialog 
1. Dump the VID and PID list with `gwmi Win32_USBControllerDevice |%{[wmi]($_.Dependent)} | Sort Manufacturer,Description,DeviceID | Ft -GroupBy Manufacturer Description,Service,DeviceID`
1. Find the device is the list