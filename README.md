# CX2000 Servo Motor Integration with Beckhoff CX8190

# Overview:
This project demonstrates the integration and control of a CX2000 series servo motor using a Beckhoff CX8190 Embedded PC with TwinCAT 2 and the TC2_MC2 motion control library.

The system covers complete implementation from hardware setup and electrical installation to PLC programming and HMI-based control.

# Features:
- Servo axis configuration and commissioning in TwinCAT 2
- Motion control using TC2_MC2 function blocks
- Beckhoff HMI interface for manual control and monitoring
- Electrical cabinet integration and wiring setup
- Structured PLC program for motion sequences

# System Architecture
Controller: Beckhoff CX8190 Embedded PC
Servo Motor: CX2000 Series
Servo Drive: Beckhoff-compatible EtherCAT servo drive
Communication: EtherCAT
Software: TwinCAT 2 (TC2_MC2 Library)

# Motion Control Implementation
The project uses standard PLCopen motion control function blocks from the TC2_MC2 library, including:

MC_Power – Enable/disable servo axis
MC_Reset – Reset faults
MC_Home – Homing sequence
MC_MoveAbsolute – Absolute positioning
MC_MoveRelative – Relative movement
MC_Stop – Controlled stop

# Example Control Flow
Power ON axis (MC_Power)
Reset faults if any (MC_Reset)
Execute homing (MC_Home)
Perform motion commands (MC_MoveAbsolute / MC_MoveRelative)
Monitor status and errors

# PLC Program Structure
Main Program (MAIN): High-level control logic
Axis Control FB: Encapsulates motion commands
Global Variables (GVL): Shared control and status variables
HMI Interface Variables: Linked to visualization

#HMI Interface
The Beckhoff HMI provides:
Servo ON/OFF control
Homing command
Position input and execution
Real-time feedback (position, status, errors)

# HMI Preview

![HMI Screen](images/hmi_servo_control.jpg)

PLC Code Snapshot
![PLC Program](images/plc_program.png)

# Electrical Cabinet Setup
The servo controller is mounted inside the electrical cabinet with proper:

Power distribution
EtherCAT wiring
Shielding and grounding
Cabinet Installation

![Cabinet Setup](images/cabinet_servo.jpg)

# Getting Started
# Prerequisites
TwinCAT 3 installed
TC2_MC2 library added
EtherCAT configured and scanned
Servo drive and motor properly wired

# Steps
Import the project into TwinCAT 2
Configure EtherCAT devices
Link axis to servo drive
Download PLC program
Run in RUN mode
Operate via HMI

# Notes
Ensure correct axis scaling and limits before motion
Verify safe torque off (STO) wiring
Perform homing before motion commands
Check fault conditions before enabling

# Applications
Conveyor positioning systems
Pick-and-place automation
Industrial motion control systems
Robotics integration
