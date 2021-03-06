# TCES_420_Final_Project

## Helpful Tutorial
* http://derekmolloy.ie/kernel-gpio-programming-buttons-and-leds/

## Kernel Tree installation
* Follow this guide > https://www.raspberrypi.org/documentation/linux/kernel/building.md
## Before Module Installation
* Check your linux kernel version

$ uname -r

* Then check your kernel tree version

$ cd your-kernel-tree

$ sudo make modules_install

* Then check the dep version number
* If the kernel version number and kernel tree version number are the same you will be able to install a module.

## Pin Setup
| Turret Pin      | Pi Pin                  | Description                                         |Input          |
| --------------- |-----------------------|---------------------------------------------------|--------------|
|Pin 3A = GPIO 04 |  GPIO_Pin # = 13        |Description :Moves the turret up in the z dimension  |   Digital High|
|Pin 4A = GPIO 17 |  GPIO_Pin # = 19        |Description :Moves the turret down in the z dimension  |   Digital High|
|Pin 1A = GPIO 27 |  GPIO_Pin # = 06        |Description: Moves Turret Counter Clockwise  |   Digital High|
|Pin 2A = GPIO 22 |  GPIO_Pin # = 05        |Description: Moves Turret Clockwise  |   Digital High|
|Pin 4A between 5V and GND |  GPIO_Pin # = 12        |Description : Rotates the Barrel and Shoots a Bullet  |   Digital High|

![alt text][logo]

[logo]: https://github.com/davidhudsont/TCES_420_Final_Project/blob/davidhv2/CES420Project4_PinLayout.png "Pin Layout"

![alt_text][logo2]

[logo2]: https://github.com/davidhudsont/TCES_420_Final_Project/blob/davidhv2/pi3_gpio.png "Pi Pin Layout"


## Module Installation
 $ git clone https://github.com/davidhudsont/TCES_420_Final_Project.git

 $ cd TCES_420_Final_Project

 $ make

 $ sudo su

 $ insmod turret.ko

* Check the dmesg to see if the turret installed

 $ dmesg

## Module Variables Location
 $ cd /sys/pi/Turret
 
* If you want to see parameters
 
 $ ls 

* If you want to see the value of each parameter use cat

 $ cat nr_missiles
* If you want to change the value of a variable e.g.

 $ echo 1 > FIRE_ALL

## Module Removal
 $ cd /home/pi/TCES_420_Final_Project

 $ rmmod turret.ko
 
* Check dmesg to see if turret uninstalled.
