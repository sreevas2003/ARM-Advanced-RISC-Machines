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
🔹 What are registers?
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
What is a pipeline?
    - Instruction execution is split into stages.
Typical ARM Pipeline
    | Stage   | Action                      |
    | ------- | --------------------------- |
    | Fetch   | Get instruction from memory |
    | Decode  | Understand instruction      |
    | Execute | Perform operation           |
📌 While one instruction executes, another is decoded → parallelism
