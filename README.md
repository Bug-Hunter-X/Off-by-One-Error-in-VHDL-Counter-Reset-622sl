# Off-by-One Error in VHDL Counter Reset

This repository demonstrates a subtle off-by-one error in a simple VHDL counter. The `bug.vhdl` file contains the buggy code, while `bugSolution.vhdl` provides the corrected version.

## Bug Description

The counter is designed to increment from 0 to 15, then reset to 0. However, the reset condition (`if internal_count = 15 then`) might lead to unexpected behavior, especially at higher clock frequencies or with certain reset sequences. The issue is that if the counter is at its maximum value (15) when the reset signal is asserted, the reset will not be properly triggered causing the counter to remain stuck at 15. 

## Solution

The solution is to modify the reset condition to explicitly set the counter to 0, using `internal_count <= 0;` , regardless of the previous state.