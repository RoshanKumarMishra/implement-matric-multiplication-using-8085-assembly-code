# Matrix Multiplication Using 8085 Assembly Language

![8085](https://img.shields.io/badge/Microprocessor-8085-blue)
![Assembly](https://img.shields.io/badge/Language-Assembly-green)
![Academic Project](https://img.shields.io/badge/Project-COA-orange)

## Overview

This project demonstrates the implementation of **Matrix Multiplication using Intel 8085 Assembly Language**. The objective is to perform matrix multiplication at the microprocessor level using the instruction set of the 8085 processor while optimizing memory usage and execution efficiency.

The project showcases how mathematical operations can be implemented using low-level programming techniques and highlights the capabilities of the 8085 microprocessor in handling arithmetic computations.


## Abstract

The project implements matrix multiplication using the Intel 8085 microprocessor architecture. The multiplication process is carried out through assembly language instructions and repeated addition techniques. The implementation demonstrates memory management, arithmetic operations, subroutine usage, and optimization techniques within the constraints of the 8085 architecture.

This project serves as an educational resource for understanding assembly language programming, computer organization, and algorithm implementation at the hardware level.

---

## Objectives

* Implement matrix multiplication using 8085 Assembly Language.
* Understand low-level arithmetic operations.
* Optimize memory usage within the limitations of the 8085 architecture.
* Demonstrate matrix handling and storage techniques.
* Explore practical applications of assembly language programming.

---

## Problem Statement

Design and implement an optimized matrix multiplication algorithm using Intel 8085 Assembly Language while:

* Minimizing memory consumption.
* Improving execution efficiency.
* Supporting matrix data storage in memory.
* Demonstrating practical use of the 8085 instruction set.
* Showcasing low-level algorithm implementation.

---

## Memory Mapping

| Memory Address | Description   |
| -------------- | ------------- |
| 8500H          | Matrix A      |
| 8600H          | Matrix B      |
| 8700H          | Result Matrix |

---

## Algorithm

### Step 1: Initialization

```assembly
MVI C,00H
LXI H,8500H
```

* Initialize register C.
* Load starting address of Matrix A into HL.

### Step 2: Load Matrix Elements

```assembly
LXI D,8600H
```

* Load starting address of Matrix B into DE.

### Step 3: Multiply Elements

* Call the MUL subroutine.
* Multiply matrix elements using repeated addition.

### Step 4: Store Intermediate Result

```assembly
MOV B,A
```

* Store multiplication result temporarily in register B.

### Step 5: Compute Dot Product

* Multiply next pair of elements.
* Add previous partial product.

```assembly
ADD B
```

### Step 6: Store Result

```assembly
CALL STORE
```

* Save the result in memory.

### Step 7: Repeat Process

```assembly
MOV A,C
CPI 04H
```

* Check whether all matrix elements are computed.
* Continue if not completed.

### Step 8: Terminate Program

```assembly
HLT
```

* Halt execution after computing all result elements.

---

## MUL Subroutine

The multiplication operation is performed through repeated addition.

### Logic

```text
Result = 0

Repeat Multiplier Times:
    Result = Result + Multiplicand

Return Result
```

---

## STORE Subroutine

Stores the computed matrix element into memory.

### Procedure

1. Set destination memory address.
2. Store accumulator contents.
3. Increment counter.
4. Return to the main program.

---

## Assembly Source Code

The complete assembly program is available in:

```text
source_code/matrix_multiplication.asm
```

---

## Project Figures

### Figure 1: 8085 Block Diagram

```text
images/fig1_8085_block_diagram.png
```

### Figure 2: Matrix Multiplication Block Diagram

```text
images/fig2_matrix_multiplication_block_diagram.png
```

### Figure 3: Multiplication of Two Numbers Flowchart

```text
images/fig3_flowchart_multiplication_of_two_numbers.png
```

### Figure 4: Multiplying Row with Column Flowchart

```text
images/fig4_flowchart_row_column_multiplication.png
```

### Figure 5: Matrix Multiplication Flowchart

```text
images/fig5_flowchart_matrix_multiplication.png
```

### Figure 6: Visual Representation of Code

```text
images/fig6_code_visualization.png
```

### Figure 7: Result on EMU8086

```text
images/fig7_result_emu8086.png
```

### Figure 8: Result on General Assembly Compiler

```text
images/fig8_result_general_assembly_compiler.png
```

---

## Results

The program was successfully executed and verified using:

* EMU8086 Emulator
* General Assembly Compiler

The resulting matrix elements were correctly generated and stored in memory.

---

## Applications

* Computer Graphics
* Linear Algebra Computations
* Scientific Computing
* Machine Learning Fundamentals
* Signal Processing
* Embedded Systems
* Educational Demonstrations

---

## Future Scope

* Support larger matrices.
* Dynamic matrix size input.
* Faster multiplication algorithms.
* FPGA implementation.
* Hardware acceleration techniques.

---

## Folder Structure

```text
Matrix-Multiplication-Using-8085/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── Project_Report.pdf
│   ├── Presentation.pptx
│   └── IEEE_Reference_Paper.pdf
│
├── source_code/
│   └── matrix_multiplication.asm
│
├── images/
│   ├── fig1_8085_block_diagram.png
│   ├── fig2_matrix_multiplication_block_diagram.png
│   ├── fig3_flowchart_multiplication_of_two_numbers.png
│   ├── fig4_flowchart_row_column_multiplication.png
│   ├── fig5_flowchart_matrix_multiplication.png
│   ├── fig6_code_visualization.png
│   ├── fig7_result_emu8086.png
│   └── fig8_result_general_assembly_compiler.png
│
├── results/
│   └── screenshots/
│
└── references/
```

---

## References

1. S. Gaonkar, *Microprocessor Architecture, Programming and Applications with the 8085*.
2. Matrix Multiplication – Wikipedia.
3. Intel 8085 Microprocessor Documentation.
4. Course materials and laboratory manuals.

---

## License

This project is developed for educational and academic purposes.
