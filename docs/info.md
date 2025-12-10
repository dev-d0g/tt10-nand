<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This design implements a simple two-input NAND gate. A NAND gate outputs 1 unless both inputs are 1, making it the inverse of the AND function.

The module begins with a standard TinyTapeout port list, which provides the dedicated inputs (ui_in) and outputs (uo_out). From these, the first two input bits ui_in[0] and ui_in[1] are used as signals A and **B`.

Inside the module, an internal wire Yd is used to hold the result of the AND operation:

and(Yd, A, B);


This intermediate signal is then passed through a NOT gate to produce the final NAND output:

not(Y, Yd);


Finally, the output Y is assigned to uo_out[0], while the remaining outputs are tied to zero. The unused I/O ports are also tied off to prevent synthesis warnings.

Overall, the design simply combines a built-in Verilog AND gate with an inverter to create a classic NAND logic function.

## How to test

Truth table:
| A | B | NAND |
|---|---|-------|
| 0 | 0 | 1     |
| 0 | 1 | 1     |
| 1 | 0 | 1     |
| 1 | 1 | 0     |

## External hardware

NONE
