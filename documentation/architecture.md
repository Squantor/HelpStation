# PickStation architecture
Architecture of the PickStation is described here
## System
The PickStation comprises of the following planned components:
* Mechanical gantry that is manually powered
* Closeup camera with illumination for visibility
* Rotatable vacuum pickup tool that is compatible with commercial tools
* Pickup nozzle rack for manual changing of nozzles
* Embedded system containing a way to accept a pick and place .pos file from kicad
* Footswitch or button to indicate next component
## Electronics
* Central control box with two USB-C inputs, one for power (requires 20V by 3A) and one for interfacing with the PC
* Internal USB hub for the various USB devices such as the microcontroller and closeup camera
* RP2040 that imitates a storage device and controls the next component indicator display and senses the switches and controls a RS485 bus
* Next component indicator display with microcontroller and RS485 bus
* Nozzle illumination
* USB camera for closeup view (aliexpress pick and place robot camera, 1080p)
Why RS485 to connect electronics? I am planning to have more intelligent tape holders, not full feeders but automatic detection of component type and indicate which component to pick next.
## Firmware
* RP2040 with USB connection as a block device/MTP and a serial port for debugging
* RS485 control interface
* RS485 display with OLED screen and few buttons
## Software
Currently no software planned but depends on KiCAD .pos files for component lists. No postprocessing needed of .pos files needed.
## Mechanical
* Main XY gantry uses 6/8mm linear bearing bars with 2020 Aluminium extrusions
* Y axis is the hand hold holder
* Vacuum pickup holder
* Tape holders
* Nozzle storage holders
