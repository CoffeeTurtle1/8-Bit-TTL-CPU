# 8-Bit TTL CPU
The goal of this project is to design (and hopefully build) a fully functional TTL CPU using 7400 series logic chips.

# The Architecture
This cpu has two RAM chips. One 256x8 RAM chip for holding data and a 65536x24 program memory chip.

## Registers
|  Register | Description |
|  ------ | ------ |
|  Program Counter (PC) | Holds the address of the next instruction to be executed |
|  Instruction Register | Holds the current instruction being executed |
|  Carry Flag | Holds the carry bit |
|  RA | General purpose register |
|  RB | General purpose register / Accumulator |

## Instruction Set
|  Address (16-bit) | Data (8-bit) | Op-Code | Instruction | Description |
|  ------ | ------ | ------ | ------ | ------ |
|  0000000000000000 | 00000000 | 0001 | ADD | Stores the sum of RA and RB in RB |
|  0000000000000000 | 00000000 | 0010 | SUB | Stores the result of RA minus RB in RB |
|  0000000000000000 | 00000000 | 0011 | JMP | Sets the value of the PC to the value of the address bits |
|  0000000000000000 | 00000000 | 0100 | JC | If the carry register is set to one the PC is set to the value of the address bits |
|  0000000000000000 | 00000000 | 0101 | LDA | Stores the value stored at the location pointed to by RA in RB |
|  0000000000000000 | 00000000 | 0110 | STA | Stores the value in RB at the location pointed to by RA |
|  0000000000000000 | 00000000 | 0111 | PUT | Stores the data bits in RB |
|  0000000000000000 | 00000000 | 1000 | INP | Stores the current value on the I/O bus in RB |
|  0000000000000000 | 00000000 | 1001 | OUT | Sets the I/O bus to the value of RB |
|  0000000000000000 | 00000000 | 1111 | HLT | Halts the CPU |

## Clock cycle
|  Cycle | Description |
|  ------ | ------ |
|  1 | Update instruction register and decode |
|  2 | Increase the program counter by one and update other registers |
|  3 | Do more stuff |
|  4 | Do more stuff |
