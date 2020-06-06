Easiest way I know is to build a kernel with the patch applied.

1. Clone kernel source:

git clone https://github.com/torvalds/linux

2.  Change directory

cd linux

3.  Checkout a version that will work with your system (5.1 is the latest I got to work with nVidia drivers in Debian stable, but the newer drivers in testing work up to 5.4)

git checkout master

4.  Apply patch

patch -p1 < /home/user/OpenRGB/OpenRGB.patch

5.  Copy your existing configuration.  I don't remember the exact filename of the existing config but it's in /boot.  Use tab-complete or a file browser to get the file name and replace "config-file" with this name below.

cp /boot/config-file .config

6.  Make oldconfig.  If it prompts for new configuration settings just hold down Enter until it's done.  This takes the default setting for any new config entries.

make oldconfig

7.  Make menuconfig to enter a UI menu that you can enable the NCT6775 driver with.  It's under Device Drivers - I2C support - I2C Hardware Bus Support - Nuvoton NCT6775 and compatible SMBus controller.  Set the NCT6775 driver setting to <M> to build it as a module.

make menuconfig

8.  Build .deb packages.  Replace X below with the number of hardware threads your CPU supports, i.e. make deb-pkg -j32 for a 16 core/32 thread CPU.

make deb-pkg -jX

9.  Once that completes, if successful, you should have several .deb files in your home directory.  Install them.

cd
sudo dpkg -i *.deb

At several points along the way it may error out from missing dependencies.  You may need to track down some packages to install with apt.  Install packages and repeat each step until successful before moving to next step.