# mano-machine-logisim
A functional Mano Machine built from scratch in Logisim Evolution, demonstrating the core principles of computer architecture and control design.
**Author:** Abdul Rafay  
**Course:** Computer Architecture Lab Project  
**Tool:** Logisim Evolution  

---

## 📘 Overview

The **Mano Machine** is a complete processor implementation of the **Basic Computer** architecture described in *M. Morris Mano’s Digital Design, Chapter 5*.  
This project was designed and verified using **Logisim Evolution**, following the principles of register transfer logic, bus-based data movement, and hardwired control.

All modules — from arithmetic units to control logic — were built from fundamental logic components, demonstrating the working of a simple stored-program computer.

---

## Architecture Overview

| Component | Description |
|------------|--------------|
| **Control Unit** | Fires Control signal to all the control pins through out the circuit at ever clockpulse |
| **Registers** | AC, DR, AR, IR, PC, TR — each implemented as a subcircuit (12, or 16 bits). |
| **Bus System** | A shared 16-bit data path connecting all registers and Memory. |
| **ALU (Arithmetic Logic Unit)** | Performs arithmetic and logical micro-operations using 16-bit Full Adder, Logic Unit, and Shifter Unit. |
| **Memory Unit** | 4096 × 16-bit memory used to store programs and data. |
| **I/O Interface** | Basic input/output implemented through INPR and OUTR registers. |

---

## Instruction Set

### Memory-Reference Instructions
| Mnemonic | Description | Example |
|-----------|--------------|----------|
| `AND` | Logical AND of AC and memory | `AND 300` |
| `ADD` | Add memory word to AC | `ADD 305` |
| `LDA` | Load memory word to AC | `LDA 310` |
| `STA` | Store AC into memory | `STA 312` |
| `BUN` | Branch unconditionally | `BUN 400` |
| `BSA` | Branch and save return address | `BSA 402` |
| `ISZ` | Increment and skip if zero | `ISZ 405` |

### Register-Reference Instructions
| Mnemonic | Description |
|-----------|--------------|
| `CLA` | Clear AC |
| `CLE` | Clear E |
| `CMA` | Complement AC |
| `CME` | Complement E |
| `CIR` | Circular right shift AC & E |
| `CIL` | Circular left shift AC & E |
| `INC` | Increment AC |
| `SPA` | Skip next if AC positive |
| `SNA` | Skip next if AC negative |
| `SZA` | Skip next if AC zero |
| `SZE` | Skip next if E zero |
| `HLT` | Halt computer |

### I/O Instructions
| Mnemonic | Description |
|-----------|--------------|
| `INP` | Input from input register |
| `OUT` | Output to output register |
| `SKI` | Skip if input flag set |
| `SKO` | Skip if output flag set |
| `ION` | Interrupt enable |
| `IOF` | Interrupt disable |

---

## Subcircuits Implemented

Below is a list of the custom subcircuits designed for modularity:

1. Register8Bit
2. Register12Bit
3. Register16Bit
4. Adder8Bit
5. Adder16Bit
6. FullAdder1Bit
7. ArithmeticUnit16Bit
8. LogicUnit16Bit
9. ShifterUnit16Bit
10. ArithmeticLogicUnit16Bit
11. Decoder2Bit
12. Decoder3Bit
13. Decoder4Bit
14. Counter4Bit
15. ControlUnit
16. ControlUnitAR
17. ControlUnitPC
18. ControlUnitDR
19. ControlUnitIR
20. ControlUnitAC
21. ControlUnitOUTR
22. ControlUnitTR
23. ControlUnitMemory
24. ControlUnitCommonBus
25. ControlUnitR
26. ControlUnitIEN
27. ControlUnitFGIO
28. ControlUnitCounter
29. ControlUnitALU
30. ControlUnitS
31. ControlUnitE
32. FullAdder4Bit
33. FullAdder12Bit
34. Register4Bit
35. Encoder3Bit
