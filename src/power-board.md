# Power Board Maintenance[^1]

## Equipment

 * Laptop
 * Small flat bladed screwdriver
 * Bench PSU
 * High-current PSU (>30A @ 12V)
 * Multimeter
 * 4× 1.3Ω--1.5Ω loads[^2]
 * Micro USB cable
 * XT60 male to fork terminals (for Bench PSU)
 * XT60 male to 7.62mm plug[^3] (for high current PSU)
 * External power connector shorting plug[^4]

## Set up

 1. Set the bench PSU to **12V±0.1V** with a **200mA±10mA** current limit.
 2. Set the multimeter to read DC voltage.

## Procedure

*Execution time*: 3 minutes per board.

 1. Tug the battery wires and check that the ring terminals are not loose and that the insulation has not pulled back.
 1. Connect the battery wires to the bench PSU.
 1. Connect the power board to the laptop with the micro USB cable.
 1. Turn on the bench PSU and the power board (don't forget the external power connector).
 1. Check that the board draws no more than **160mA**.
 1. Check that the 5V output measures **5V±200mV**.
 1. Check that the fan is spinning.
 1. Slowly turn the bench PSU voltage down to **9V**. When passing **10.2V±10mV** the power board should shut off all outputs and start flashing the **flat** LED. When passing **9.6V±10mV** the power board should turn off completely.
 1. Slowly turn the bench PSU voltage up to **12V**. When passing **11.1V±100mV** the power board should turn back on.
 1. Turn off the bench PSU and power board.
 1. Connect the battery wires to the high current PSU.
 1. Connect the dummy loads to the power board outputs `H0`, `H1`, `L0` and `L1`.
 1. Turn on the high current PSU and the power board.
 1. Run `./scripts/power_test.py` and follow the instructions.

[^2]: 1.5Ω 100W resistor (or 7× 10Ω 15W resistors in parallel) to 7.5mm camcon plug (Farnell 3882275)
[^3]: Farnell 1793033
[^4]: 5mm camcon plug (Farnell 3881854) shorted
