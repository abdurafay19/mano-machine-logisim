# mano-machine-logisim
A functional Mano Machine built from scratch in Logisim Evolution, demonstrating the core principles of computer architecture and control design.

**At a glance:** 16-bit stored-program CPU · 25 instructions · 35 custom subcircuits · 4K × 16 memory · hardwired control

## Demo

<!-- TODO: Add a GIF of a program running on the Mano Machine, e.g. ![Demo](./screenshots/demo.gif) -->

**Author:** Abdul Rafay  
**Course:** Computer Architecture Lab Project  
**Tool:** Logisim Evolution  

---

## Overview

The **Mano Machine** is a complete processor implementation of the **Basic Computer** architecture described in *M. Morris Mano’s Computer System Architecture, Chapter 5 (Basic Computer Organization and Design)*.  
This project was designed and verified using **Logisim Evolution**, following the principles of register transfer logic, bus-based data movement, and hardwired control.

All modules — from arithmetic units to control logic — were built from fundamental logic components, demonstrating the working of a simple stored-program computer.

---

## Architecture Overview

| Component | Description |
|------------|--------------|
| **Control Unit** | Generates the control signals for every register, the bus, memory, and the ALU on each clock pulse (hardwired control). |
| **Registers** | AC, DR, AR, IR, PC, TR, INPR, OUTR — each implemented as a subcircuit (8, 12, or 16 bits). |
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
5. FullAdder16Bit
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


Each module was constructed using basic logic gates and multiplexers to simulate microoperations accurately.

---

## Circuit Snapshots

### Main CPU View
![Main Circuit](./screenshots/main_circuit.png)

### ALU Module
![ALU Module](./screenshots/ALU_module.png)

---

## Testing and Verification

All **hexadecimal programs from Morris Mano’s textbook** were loaded into the memory and executed successfully.  
Each instruction was verified step-by-step using the manual clock and control signals.

✅ Achieved **Full Marks** for correctness and design clarity.

---

## How to Run

1. Install "Logisim Evolution".
2. Open `Processor.circ` in Logisim Evolution.
3. Load program memory with your `.hex` file.
4. Start the clock or use manual stepping to observe instruction execution.
5. Monitor the registers and bus signals to see program flow in real time.

---

## Author

**Abdul Rafay**  
Computer Architecture Lab Project  
[GitHub Profile](https://github.com/abdurafay19)
[LinkedIn Profile](https://www.linkedin.com/in/abdurafay19)

---

## Academic Integrity Notice

© 2025 Abdul Rafay — All Rights Reserved.  
This project is published for educational viewing only.

Reusing, modifying, or submitting this work (in whole or in part) for any
academic assessment, coursework, or lab project by others is strictly
prohibited and may constitute academic misconduct.



