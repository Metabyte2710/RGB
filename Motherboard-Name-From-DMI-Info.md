[[_TOC_]]

# How to find them

The easiest way to grab the Vendor and Motherboard information is from DMI info. The DMI information holds several key pieces of data specific to the computing platform you're using.

## Linux

1. Open your favourite terminal or login to the CLI
1. type `cat /sys/devices/virtual/dmi/id/board_vendor && cat /sys/devices/virtual/dmi/id/board_name`
1. Copy your Motherboard name as needed

## Windows

1. Run Powershell by hitting window key + R
1. Type `powershell` in the run dialog 
1. Dump the motherboard details with `Get-WmiObject Win32_BaseBoard`
1. The Motherboard name is the "Product"
