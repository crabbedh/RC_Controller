# RC_Controller by Crab Consulting
RC Controller for ESP32 projects   July '24

This repository contains the KiCad generated Gerber files for a PCB
that offers a general purpose ESP32 controller suitable for small RC
projects, such as Skid Steers, Dump Trucks, cars, etc. There were a few design
goals for the creation of this PCB.
0. designed for the ESP32 DevKit V1 module from EspressIF
1. small size
2. supports 4 motors or devices that can use motor outputs
3. readily available components from AliExpress
4. support for a "Power Switch" to allow the CPU to shut off power
5. support for offboard 2S powersource (7-9v ideal)
6. ability to monitor state of power source
7. supports 3 servos
8. supports one general purpose analog input (12 bit ADC from 0-3.3v)
9. Pads are very "DIY friendly", meaning they are optimally designed to be
    easy for soldering and creating a proper solder fillet. I use 1mm solder.

The PCB supports a Pololu 2808 power switch, or a physical Slide switch. (pololu.com)
It uses 2 DRV8833 motor driver boards which can each control 2 motors/devices

This is currently in beta and all features are not yet present. For instance, I have not
added the ability to use a physical slide switch. I am testing this board with
a few of the ProfessorBoots models and will post a more tested general release within a few weeks. 

While anyone is welcome to download and test this PCB, no support is provided as it
is purely in beta status.

I've included pinout diagrams of parts required by this board.

bigDumpv*.zip is the arduino IDE code for the Prof Boots mini-dump RC model (large one). This code
should work with the Prof Boots PCB and with the RC_Controller PCB here. The battery monitor and
remote power off obviously won't work with the Prof Boots PCB as this doesn't have the necessary
hardware.

Dave Crabbe
