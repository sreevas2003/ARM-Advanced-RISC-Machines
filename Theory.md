## CPU Instruction Types
```
All processors are broadly classified into two instruction design philosophies:
🔹 RISC - Reduced Instruction Set Computer
🔹 CISC - Complex Instruction Set Computer

Instruction Type
│
├── RISC
│   ├── ARM
│   │   ├── Cortex-M -- Microcontrollers --- Example: STM32, NXP LPC
│   │   ├── Cortex-R -- Hard real-time --- Automotive ECUs
│   │   ├── Cortex-A -- Application processors --- Example: Raspberry Pi, Smartphones
│   │   └── Neoverse -- Servers & cloud --- Example: AWS Graviton
│   ├── RISC-V
│   ├── MIPS
│   └── SPARC
│
└── CISC
    └── x86
        ├── Intel
        └── AMD
```
## RISC vs CISC (ARM vs x86)
```
| Feature                | RISC (ARM)                | CISC (x86)   |
| ---------------------- | ------------------------- | ------------ |
| Instruction size       | Fixed                     | Variable     |
| Cycles per instruction | 1 (mostly)                | Multiple     |
| Power consumption      | Low                       | High         |
| Hardware complexity    | Simple                    | Complex      |
| Used in                | MCU, Mobile, IoT, Servers | PCs, Laptops |
| Example                | ARM Cortex                | Intel / AMD  |

```

## 1️⃣ What is ARM Architecture?
```
- ARM stands for Advanced RISC Machine.
- ARM architecture is a CPU design based on RISC principles, optimized for low power, high efficiency, and scalability.
```
### Key characteristics
```
  - RISC-based (simple instructions)
  - Low power consumption
  - High performance per watt
  - Scalable (tiny MCUs → powerful servers)
  - Large ecosystem support
```
### Why ARM was created
```
- Early computers consumed too much power

Embedded systems needed:
    * Low heat
    * Long battery life
    * Cheap hardware
```
## ARM Core (CPU Core)
```
🔹 What is an ARM Core?
    - The processing engine
    - Executes instructions
    - Designed by ARM
    - Licensed to chip manufacturers
🔹 Core Types
| Core     | Purpose                |
| -------- | ---------------------- |
| Cortex-M | Microcontrollers       |
| Cortex-R | Real-time safety       |
| Cortex-A | Application processors |
| Neoverse | Server / Cloud         |
```
# ARM Architecture
- ## Core Building Blocks of an ARM CPU
```
An ARM CPU internally has:
🔹 Main Components
    - Registers
    - ALU (Arithmetic Logic Unit) 
    - Control Unit
    - Pipeline
    - Load/Store Unit
    - Interrupt & Exception Logic
    - Memory Interface
```
- ## Registers (Fastest Memory in CPU)
What are registers?
    - Small storage inside CPU
    - Used to hold data & addresses
    - Faster than RAM
```
| Register | Name            | Purpose                    |
| -------- | --------------- | -------------------------- |
| R0–R12   | General purpose | Data, variables, arguments |
| R13      | SP              | Stack Pointer              |
| R14      | LR              | Link Register              |
| R15      | PC              | Program Counter            |
```
**R0 – R12 (General Purpose Registers)**
```
Used to store:
    - Variables
    - Function arguments
    - Temporary values
    - Addresses
```
**R13 – Stack Pointer (SP)**
```
Points to top of stack
Stack stores:
    - Local variables
    - Return addresses
    - Saved registers
```
**R14 – Link Register (LR)**
```
    - Stores return address of a function
    - Set automatically on BL (Branch with Link)
```
**R15 – Program Counter (PC)**
```
Holds address of next instruction
Auto-increments
Changes on:
    - Branch
    - Interrupt
    - Exception
📌 CPU execution is driven entirely by Program Counter.
```
**Special Registers (Related but Important)**
```
Although not in R0–R15 list, these are critical:
    - xPSR → Status flags (Zero, Carry, Negative)
    - CONTROL → Privilege & stack select
    - MSP / PSP → Main & Process stack pointers (Cortex-M)
```
- ## Load–Store Architecture
    - Only LOAD and STORE instructions access memory
    - All calculations happen inside registers
- ## Pipeline (How ARM Executes Fast)
```
What is a pipeline?
    - Instruction execution is split into stages.
Typical ARM Pipeline
    | Stage   | Action                      |
    | ------- | --------------------------- |
    | Fetch   | Get instruction from memory |
    | Decode  | Understand instruction      |
    | Execute | Perform operation           |
📌 While one instruction executes, another is decoded → parallelism
```
# ARM Instruction Set
### What is the ARM instruction set?
```
It is the set of machine instructions that an ARM CPU understands and executes.
ARM instructions are:
- RISC-based
- Mostly 32-bit (ARM) or 16/32-bit (Thumb)
- Load–Store architecture
```
### ARM Instruction Format (32-bit ARM)

<img width="565" height="244" alt="image" src="https://github.com/user-attachments/assets/22e62b7e-f7a3-4bef-a5a5-6c01e41d20fe" />

Each field means:
- Cond → Condition to execute
- Opcode → Operation (ADD, SUB, MOV…)
- Rd → Destination register
- Rn → Source register
- Operand2 → Immediate or register
📌 Every ARM instruction can be conditional (very powerful).

### Thumb & Thumb-2
**Why Thumb exists**
```
- ARM 32-bit instructions = fast but large code size
- Thumb = smaller instructions, better for embedded systems
```
**Thumb vs Thumb-2**
```
| Feature          | Thumb    | Thumb-2      |
| ---------------- | -------- | ------------ |
| Instruction size | 16-bit   | 16 + 32 bit  |
| Performance      | Medium   | Near ARM     |
| Code size        | Small    | Small        |
| Used in          | Cortex-M | Cortex-M / A |
📌 Cortex-M runs ONLY Thumb/Thumb-2
```
### Data Processing Instructions
**Common instructions**
| Instruction | Meaning     |
| ----------- | ----------- |
| MOV         | Copy        |
| ADD         | Addition    |
| SUB         | Subtraction |
| AND         | Logical AND |
| ORR         | Logical OR  |
| EOR         | XOR         |
| CMP         | Compare     |
| TST         | Test bits   |
**Example**
```
Internal flow:
- Read R1 & R2
- ALU adds
- Result → R0
- Flags updated (optional)
```
### Load / Store Instructions

<img width="262" height="208" alt="image" src="https://github.com/user-attachments/assets/0be65abd-1407-4669-bedc-aa18371e7d6c" />

* ARM never operates directly on memory
| Instruction | Meaning                 |
| ----------- | ----------------------- |
| LDR         | Load memory → register  |
| STR         | Store register → memory |
| LDM         | Load multiple           |
| STM         | Store multiple          |

### Branch Instructions
| Instruction | Use                   |
| ----------- | --------------------- |
| B           | Jump                  |
| BL          | Function call         |
| BX          | Return / state switch |
### Conditional Execution (ARM Superpower)

<img width="861" height="325" alt="image" src="https://github.com/user-attachments/assets/cf603f91-ab16-4c50-9216-b2a77309d5a1" />

**Condition Codes**

| Code | Meaning       |
| ---- | ------------- |
| EQ   | Equal         |
| NE   | Not equal     |
| GT   | Greater       |
| LT   | Less          |
| GE   | Greater/equal |
| LE   | Less/equal    |
| AL   | Always        |


