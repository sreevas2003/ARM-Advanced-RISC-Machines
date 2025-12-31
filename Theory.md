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
