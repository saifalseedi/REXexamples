﻿Stepping controller 
===================

This folder contains the source files for the demonstration project on stepper
motor control in REX.

The stepper motor is controlled by continuous PID controller (PIDU block) and stepping 
controller with velocity input (SCUV block). In this example, the motorized 
valve drive (MVD block) used to regulate the pipes flow is controlled.

User can change the set-point with the CNR_sp block and observe the trends of
important values in the system. It is necessary to set the CNB_MAN block for
manual control. After that, it is possible to control the MVD unit with MP_UP and 
MP_DN blocks.

## Timing of the project ##

The algorithm runs each 100 milliseconds (0.1 s). See the EXEC function block,  
tick x ntick0 = 0.05 x 2 = 0.1 

## Prerequisites ##
- RexCore must be installed and running on the target device.

## Running the example ##
- The **exec.mdl** file is the project main file.
- Open it with *RexDraw*.
- Check that the motor time constant (SCUV:trun parameter) is set according to 
valve speed (MVD:tv parameter).
- Make sure that the icotype parameter of the PIDU controller is set to 4:SCUV.
- Compile and download the project to the target device.
- Switch to online mode and watch the algorithm.
- Open trend diagnostic window for the block TRND_Step.
- Change the set point (CNR_sp) in interval from 0 to 1. The input to the process
is shaped by pulses generated by SCUV block processed in MVD valve.

## Documentation ##

- **Press F1 for help** on the selected function block in the *RexDraw* program.
- [PIDU function block documentation](https://www.rexcontrols.com/media/2.50.4/doc/ENGLISH/MANUALS/BRef/PIDU.html)
- [SCUV function block documentation](https://www.rexcontrols.com/media/2.50.4/doc/ENGLISH/MANUALS/BRef/SCUV.html)
- [Function blocks of REX](https://www.rexcontrols.com/media/2.50.4/doc/ENGLISH/MANUALS/BRef/BRef_ENG.html)
- [RexDraw User Guide](https://www.rexcontrols.com/media/2.50.4/doc/ENGLISH/MANUALS/RexDraw/RexDraw_ENG.html)
- [Complete documentation of REX](http://www.rexcontrols.com/documentation-and-support)

## Additional information ##

- Visit the [REX Controls company webpage](http://www.rexcontrols.com) 
for more information about the example projects and developing advanced 
automation and control solutions using REX.