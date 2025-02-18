# Verilog Review for Programmers

This cheat sheet covers basic Verilog for hardware design, as presented in the notebook.

## Background & Overview
ASICs - application specific, baked in, custom designed, for single purpose, cheaper for mass production
FPGAs - Programmable chips, for multiple purposes/design/prototypes, expensive for mass production
Both works with verilog code.
### Terminology
- **Structural Description** (Netlist/Gatelevel/transistor level) - detail to gates
- **Behavioral Description** - Describe functionality without gate specification (looks like c)
- **Testing description** designed for simulation
- HDLs (Verilog, VHDL)

## Fundamentals
### comments
- single-line comments `//`
- mulit-line coments `/* ...*/`
### operators
- Unary = `a = ~b;`
- Binary =  `a = b & c;`
- Ternary `a = (b<c)? b : c;`
### Encapsulation
```verilog
module and_gate (
  input  in1, in2,
  output  out);

  <module internals>

endmodule
```
## Structural Verilog
example
```verilog
module xor_gate(
  input a, b,
  output z);

  wire abar, bbar, t1, t2;

  not invA (abar, a);
  not invB (bbar, b);
  and and1 (t1, a, bbar);
  and and2 (t2, b, abar);
  or or1 (z, t1, t2)
endmodule
```
This is:
![example image](xor-gate-example.png)
## Behavioral Verilog
