## Three-Phase Induction Motor Drive using SPWM Inverter (Simulink)
A MATLAB/Simulink model of an open-loop ,three-phase voltage source inverter (VSI)
driving a squirrel-cage induction motor. sinusoidal pulse-width modulation(SPWM) is used to generate Gate signal.

## Overview 

The model converts a 500 V DC supply into a variable frequency three phase AC supply using a six-MOSFET bridge.
The inverter feeds an asynchronus machine loaded with a constant mechanical torque , and the rotor speed is displayed in rpm.

# System Discription

## Power stage 
- DC source : 500 V ideal voltage source
- -Inverter : three-leg ,six-MOSFET bridge (each with a antiparallel body diode)
- Load : three-phase asynchoronus machine (per-unit parameters)

### Control /Gating 
- A MATLAB Function block generates three-phase sinusoideal refernce
- signals (R,Y,B), 120° apart, from simulation time and a frequency input
  (60 Hz base frequency with a scaling gain).
- Each reference is compared ('.' relation operator ) with a triangular carrier wave to produce the PWM gate pulse for the upper switch.
- The lower switch of each leg receieves the inverted (NOT) signal, giving complementary switching

  ## Motor Parameters (pu(
  -Nominal power -3.7 KVA
  -Nominal voltage  -460V rms
  -frequency - 60Hz
  -Stator Rs ,Lls - 0.01965 ohm ,0.0397 H
  -Rotor Rr ,Llr - 0.01909 ohm ,0.0397 H
  Mutual inductance Lm -1.354 H
  Inertial H ,friction F ,pole pairs p - 0.0926kg⋅m² , 0.05479N ,2

##Load and Measurement 
- Constant mechanical torque input : 10Nm
- -Rotor speed (wm) is converted into radian using gain block and shown using display block
## Requirements
-MATLAB and Simulink 
-simscape Electrical (Specialized Power Systems) 
##How to Run 
1 Clone the repository .
2 Open the '.slx' model file in simulink.
3 Run the simulation (the 'powergui' is set to Continuous mode).
4 View rotor speed on the scope and Display block .

##Possible Extensions
-Closed-loop speed control (field -oriented control)
-Harmonics (THD) analaysis of inverter output voltage and current 
-Torque and stator current waveform analysis
  
