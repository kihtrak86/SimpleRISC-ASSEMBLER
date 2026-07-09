# SimpleRISC Assembler

A **Python-based two-pass assembler** for the **SimpleRISC** Instruction Set Architecture (ISA). The assembler translates SimpleRISC assembly programs into **32-bit binary machine code** by performing instruction parsing, symbol table generation, label resolution, and machine code encoding.

This project is intended for educational purposes to demonstrate the working principles of a basic assembler used in computer architecture.

---

## Features

* Two-pass assembler implementation
* Converts SimpleRISC assembly into 32-bit binary machine code
* Supports arithmetic, logical, memory, and branch instructions
* Resolves labels using a symbol table
* Supports register and immediate operands
* Performs basic syntax validation
* Generates machine code in a binary output file

---

## Project Structure

```text
Simple_RISC_Assembler/
│
├── SimpleAssembler/
│   ├── assembler.py
│   ├── input.asm
│   └── output.bin
│
├── README.md
└── Rules.txt
```

---

## Supported Instructions

### Arithmetic Instructions

* ADD
* SUB
* MUL
* DIV
* MOD

### Logical Instructions

* AND
* OR
* NOT
* MOV
* CMP

### Shift Instructions

* LSL
* LSR
* ASR

### Memory Instructions

* LD
* ST

### Branch Instructions

* B
* BEQ
* BGT
* CALL
* RET

### Other Instructions

* NOP

---

## Assembler Workflow

The assembler follows a **two-pass assembly process**.

### Pass 1

* Reads the assembly source file.
* Removes comments and blank lines.
* Detects labels.
* Creates a symbol table containing label addresses.

### Pass 2

* Parses each instruction.
* Resolves branch labels using the symbol table.
* Encodes instructions into 32-bit machine code.
* Writes the generated binary instructions to the output file.

---

## Requirements

* Python 3.x

No external libraries are required.

---

## Usage

Navigate to the assembler directory.

```bash
cd SimpleAssembler
```

Run the assembler.

```bash
python assembler.py input.asm output.bin
```

where:

* `input.asm` – Assembly source file
* `output.bin` – Generated binary machine code

---

## Example

### Input (`input.asm`)

```asm
START:
MOV R1 10
MOV R2 20
ADD R3 R1 R2
CMP R3 30
BEQ END
NOP
END:
RET
```

### Output (`output.bin`)

```text
01001100010000000000000000001010
01001100100000000000000000010100
00000000110001001000000000000000
00101100000011000000000000011110
10000000000000000000000000000110
01101000000000000000000000000000
10100000000000000000000000000000
```

---

## Error Handling

The assembler reports errors for:

* Invalid instruction names
* Undefined labels
* Invalid instruction formats
* Invalid register syntax
* Invalid operand types

---

## Current Limitations

* Register numbers are not range-checked.
* Immediate values are not checked for overflow.
* Negative immediate values are not supported.
* Hexadecimal (`0x`) and binary (`0b`) literals are not supported.
* Data directives (`.data`, `.word`, etc.) are not implemented.
* Pseudo-instructions and macros are not supported.

---

## Future Improvements

* Register range validation
* Immediate overflow detection
* Support for signed immediate values
* Hexadecimal and binary literals
* Additional assembler directives
* Hexadecimal output generation
* Improved error reporting with line numbers
* Unit testing

---

## Technologies Used

* Python 3

---

## License

This project is intended for educational and learning purposes.
