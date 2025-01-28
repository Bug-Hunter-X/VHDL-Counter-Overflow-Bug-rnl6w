# VHDL Counter Bug Report

This repository contains a VHDL code example demonstrating a common error in counter implementation: potential integer overflow. The `buggy_counter.vhdl` file shows the flawed code, while `fixed_counter.vhdl` provides a corrected version.

## Bug Description

The original code uses a standard integer type for the counter.  While functional in simulation, this may lead to unexpected behavior or synthesis issues:

1. **Synthesis Problems:** Depending on the target FPGA or ASIC, standard integers may not be directly synthesizable into efficient hardware counters.
2. **Overflow:** If the counter reaches its maximum value (15 in this case), incrementing it may lead to unpredictable behavior (overflow).

## Solution

The corrected code in `fixed_counter.vhdl` addresses this using an unsigned type for the counter, offering improved synthesis and prevents overflow by wrapping around.
