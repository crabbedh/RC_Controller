# RC_Controller by Crab Consulting
RC Controller for ESP32 projects   July '24

![](https://github.com/crabbedh/RC_Controller/blob/main/pcbv2Image.jpeg)

--------->  V2 of PCB Gerber & Schematic now released (shown above)
Please use this version

* Beta Testing & BUG LISTING at end of this readme **********

This repository contains the KiCad generated Gerber files for a PCB
that offers a general purpose ESP32 controller suitable for small RC
projects, such as Skid Steers, Dump Trucks, cars, etc. There were a few design
goals for the creation of this PCB.

0. designed for the ESP32 DevKit V1 module from EspressIF
1. small size
2. supports 4 motors or devices that can use motor outputs
3. readily available components from AliExpress
4. support for a "Power Switch" to allow the ESP32 to shut off power
5. support for offboard 2S powersource (7-9v ideal)
6. ability to monitor voltage of power source
7. supports 3 servos
8. supports one general purpose analog input (12 bit ADC from 0-3.3v)
9. Drop in replacement for the ProfessorBoots larger MiniDump model and
    "Tracker" Mini Skidi, using my remixed chassis. Both Tested.
     https://www.printables.com/model/948849-mini-dump-v3-power-remix
   
     https://www.printables.com/model/896776-tracker-skidsteer-tank-track-version-evolution
   
11. Pads are very "DIY friendly", meaning they are optimally designed to be
    easy for soldering and creating a proper solder fillet. Recommend 0.8 to 1mm 63/37 solder.

The PCB supports a Pololu 2808 power switch, or a physical Slide switch. (pololu.com)
It uses 2 DRV8833 motor driver boards which can each control 2 motors/devices

Everything here is free to use, except for commercial purposes. Don't post on other sites, just link this page.

I've included pinout diagrams of parts required by this board.

To order this board, simply download the gerber ZIP file and drag it into the home screen of JLCPCB.COM. 
You can order 5 boards for a crazy cheap price. You can also choose very cheap global shipping. I recommend
creating an account so you have a history of the order and can view its status. (at time of writing
I received 5 boards for $6 Cdn, $4 US which I received in about 2 weeks)

bigDumpv*.zip is the PS3 Controller version (arduino IDE) code for the Prof Boots mini-dump RC model (large one). This code
will work with the Prof Boots PCB and with the RC_Controller PCB here (you may have to change port 
designations to match your setup. The battery monitor and
remote power off obviously won't work with the Prof Boots PCB as this doesn't have the necessary
hardware.

ultimateSkidi.zip is arduino code for the PS3 Controlled, Tracker Skidi and using my RC_Controller board. It gives
an example of adding many features to the basic skidi with software. It can be used with the V2 or V3
Prof Boots PCB by changing the port designations for servos/motors and setting feature flags to false.

Dave Crabbe

********* V2 Release *******************
Changed from GPIO 5 to GPIO 27 for driving motor as 5 stayed high after reboot
Moved Motor solder points higher and repositioned to better fit into holder in Skid Steer model
Added physical switch alternative to Pololu 2808 (Pololu recommended)
Added ground plane on bottom

********* Beta Testing *****************

Initial tests are great. No errors in the PCB. I've used board in both the larger Mini-Dump and in my "Tracker" remix of the mini-skidi

******** Beta BUGS *********************

I used ESP32 Pin #5 for an input to a Motor Controller and should not have. This pin goes high on reboot. If you have this on a motor,
the motor will operate until the code initializes that pin as an output. About 3-5 seconds. In the next iteration, I'll use D27 instead
which should not exhibit this behavior. 
