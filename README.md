Task 5 
# Advanced Easy to Use Burglar Alarm

This project implements a burglar alarm using an ultrasonic sensor and a microcontroller board.

## Overview
The Burglar Alarm detects objects using an HC-SR04 ultrasonic sensor, providing an alert via a passive buzzer when intrusion is detected. It operates on low power (5V DC) and is easy to install.

## Components Required
- VSD Squadron Mini development board
- HC-SR04 Ultrasonic Sensor
- Breadboard
- Male-to-Male, Male-to-Female jumper cables
- Red LED
- Passive Buzzer
- 220 Ohm Resistor
- Toggle Switch

## Circuit Diagram
[Insert Circuit Diagram Image or Link Here]

## Pin Connection Table
| HC-SR04 Ultrasonic Sensor Pin | VSD Squadron Mini Pin |
|-------------------------------|-----------------------|
| VCC                           | 5V                    |
| Trig                          | PD3                   |
| Echo                          | PD2                   |
| Gnd                           | Gnd                   |
| LED +                         | PD4                   |
| LED - (via 220Ω Resistor)     | Gnd                   |
| Buzzer Pin 1                  | PC7                   |
| Buzzer Pin 2                  | Gnd                   |
| Button Switch Pin 1           | 5V                    |
| Button Switch Pin 2           | PC3                   |

## Installation
1. Connect components according to the circuit diagram.
2. Upload the provided code (`main.c`) to your VSD Squadron Mini board.
3. Power the system using a 5V DC adapter or battery bank.

## Usage
1. Turn on the device and wait for auto-adjustment (LED lights up).
2. Once calibrated, the alarm is ready to detect intrusions.
3. Press the button to activate monitoring.
4. Adjust the threshold as needed based on average distance readings.


