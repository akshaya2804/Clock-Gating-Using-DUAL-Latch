# Clock-Gating-Using-DUAL-Latch

Overview

This project implements a clock gating circuit in Verilog to control the clock signal based on an enable signal. Clock gating is a power-saving technique used in digital circuits to disable the clock signal to certain parts of a design when they are not in use. A corresponding testbench verifies the functionality of the clock gating module.

Key Components

clock_gating Module:

Implements the clock gating functionality using two latches and an AND gate.
Outputs a gated clock signal (gated_clk) based on the clk and enable signals.

tb_clock_gating Testbench:

Provides a clock signal and toggles the enable signal to test the clock gating behavior.
Monitors and displays the outputs to verify functionality.

It Works

Clock Gating Circuit:

The circuit uses two latches:
Latch 1 is triggered on the positive edge of the clock or when the enable signal is de-asserted.
Latch 2 is triggered on the negative edge of the clock or when the enable signal is de-asserted.
The outputs of the two latches are combined using an AND gate to generate the gated clock signal.

Testbench Functionality:

The testbench generates a clock signal (clk) with a period of 10 time units.
The enable signal (enable) is toggled at specific intervals to test the behavior of the gated clock output.
The $monitor statement logs the simulation time, clk, enable, and gated_clk values.

Output
The output of the testbench displays the simulation time and the state of the signals:


Time = 0, clk = 0, enable = 0, gated_clk = 0
Time = 5, clk = 1, enable = 0, gated_clk = 0
Time = 10, clk = 0, enable = 1, gated_clk = 0
Time = 15, clk = 1, enable = 1, gated_clk = 1
Time = 20, clk = 0, enable = 1, gated_clk = 1
...
The gated_clk signal is active (follows the clock) only when enable is asserted (1).
