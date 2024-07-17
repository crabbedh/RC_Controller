# RC_Controller by Crab Consulting
RC Controller for ESP32 projects   July '24

This repository contains the KiCad generated Gerber files for a PCB
that offers a general purpose ESP32 controller suitable for small RC
projects, such as Skid Steers, Dump Trucks, cars, etc. 

The PCB supports a Pololu 2808 power switch, or a physical Slide switch. 
It accepts 2 DRV8833 motor driver boards which can each control 2 motors/devices

It provides 2 ports for servos and a general purpose analog input monitor port

It is designed to work with a 2S battery (8.4v). View the schematic file for details.

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
