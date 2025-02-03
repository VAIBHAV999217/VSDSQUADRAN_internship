# VSD_RISK V_internship
1-month Research Internship on VSD Squadron Mini based on RISC-V, the board is powered by a CH32V003F4U6 chip with a 32-bit RISC-V core.
 
 Intern Name # Vaibhav Revankar #
 
 College # SJB INSTITUTE OF TECHNOLOGY #
 
 Course Instructor # Kunal Ghosh #
 This VSDSquadron Mini-Internship program introduces participants to the world of VLSI chip design and RISC-V architecture using open-source tools. It provides a practical, hands-on learning experience centered around the VSDSquadron Mini RISC-V Development Board.The development board is equipped with a 32-bit RISC-V core, 16KB of flash memory, and 2KB of SRAM, operating at a clock speed of 24MHz. It features 15 GPIO pins for hardware interfacing and supports widely-used communication protocols such as I2C, SPI, and USART, making it versatile for a range of projects. These capabilities allow participants to build and prototype hardware applications while deepening their understanding of the RISC-V ecosystem.
<details>
<summary><b>Task 1:</b> Installing RISC-V toolchain and Refer to C and RISC-V based lab videos </summary>   
<br>

 C-Based Lab
 ----
Install leafpad editor for C programming using command

 ```
         sudo apt  install leafpad
 ```
``` 
![install leafpad](https://github.com/user-attachments/assets/69a4702e-69e4-494d-8bb0-4a9f347eee5b)

```

Write a program that gives the sum of n numbers using C in leafpad editor."sum1ton.c" is the filename

 ```![overleaf sum1ton](https://github.com/user-attachments/assets/9b683e34-7296-4785-889d-fc1b85038656)```

 After Compiling C code save ``ctrl+s`` and close the window ``ctrl+w`` 

 Run the program and check the results using commands
 ````
gcc sum1ton.c
./a.out 
````
./a.out is used for result

result :

![c result ](https://github.com/user-attachments/assets/78b285ae-7b20-4409-acd1-4d8e9ebccf8c)
</details>

<details>
<summary><b>Task 3:</b> 1) "List various RISC-V instruction type (R, I, S, B, U, J) after going through RISC-V software documentation
2) Identify 15 unique RISC-V instructions from riscv-objdmp of your application code 
3) Identify exact 32-bit instruction code in the instruction type format for 15 unique instructions
4) Upload the 32-bit pattern on Github"</summary>   
<br>
 
The RV32I instruction set architecture (ISA) in RISC-V is made up of several types of instructions, which can be classified based on their functionalities and encoding formats. Below is a summary and classification of the various instructions, their groupings by bits, and the combinations defined for each function in the recent RV32I specification (May 2024).

### Types of Instructions in RV32I:
- **R-Type Instructions**
- **I-Type Instructions**
- **S-Type Instructions**
- **B-Type Instructions**
- **U-Type Instructions**
- **J-Type Instructions**

![WhatsApp Image 2024-12-06 at 15 45 43_7140aa82](https://github.com/user-attachments/assets/02cee157-e459-47ee-a6b9-d199ba388c78)

Ref: The RISC-V Instruction Set Manual Volume I | © RISC-V

---

## R-Type Instruction Format

| **Bit**  | 31-25      | 24-20     | 19-15     | 14-12     | 11-7      | 6-0       |
|----------|------------|-----------|-----------|-----------|-----------|-----------|
| **Field**| funct7     | rs2       | rs1       | funct3    | rd        | opcode    |
| **Description** | Function code (extended operation) | Source Register 2  | Source Register 1  | Function code (defines operation) | Destination Register  | Operation code  |

![WhatsApp Image 2024-12-06 at 16 52 58_88180d42](https://github.com/user-attachments/assets/62d18328-66d8-461d-91f5-af4d9991ec49)

---

## I-Type Instruction Format

| **Bit**  | 31-20      | 19-15     | 14-12     | 11-7      | 6-0       |
|----------|------------|-----------|-----------|-----------|-----------|
| **Field**| imm[11:0]        | rs1       | funct3    | rd        | opcode    |
| **Description** | Immediate bits [11:0] | Source Register 1 | Function code (defines operation) | Destination Register | Operation code |

![WhatsApp Image 2024-12-06 at 16 57 30_40e1abd6](https://github.com/user-attachments/assets/3e567cf2-00eb-4711-b30e-c760c5402fc4)

---

## S-Type Instruction Format

| **Bit**  | 31-25      | 24-20     | 19-15     | 14-12     | 11-7      | 6-0       |
|----------|------------|-----------|-----------|-----------|-----------|-----------|
| **Field**| imm[11:5]  | rs2       | rs1       | funct3    | imm[4:0]  | opcode    |
| **Description** | Immediate bits [11:5]  | Source Register 2 | Source Register 1 | Function code (defines operation) | Immediate bits [4:0]  | Operation code |

![WhatsApp Image 2024-12-06 at 17 45 13_a0fbc9ab](https://github.com/user-attachments/assets/c330e2d7-7bb2-4de2-adf2-5df40744aa8a)

---

## B-Type Instruction Format

| **Bit**  |    31     | 30-25     | 24-20     | 19-15     | 14-12      | 11-8       |    7     | 6-0       |
|----------|------------|-----------|-----------|-----------|-----------|-----------|---------|---------|
| **Field**| imm[12]    | imm[10:5]       | rs2       | rs1    | funct3 | imm[4:1]  | imm[11] | opcode |
| **Description** | Immediate bit [12] | Immediate bits [10:5] |  Source Register 2 | Source Register 1 | Function code (defines operation) | Immediate bits [4:1] | Immediate bit [11] | Operation code |

![WhatsApp Image 2024-12-06 at 17 07 25_e8674253](https://github.com/user-attachments/assets/4c8c579e-7866-460b-bf88-f5c4b0ed3e33)


---

## U-Type Instruction Format

| **Bit**  | 31-12      | 11-7      | 6-0       |
|----------|------------|-----------|-----------|
| **Field**| imm[31-12] | rd        | opcode    |
| **Description** | Immediate bits [31-12] | Destination Register | Operation code |

![WhatsApp Image 2024-12-06 at 17 54 28_8d65a2a1](https://github.com/user-attachments/assets/27904b7f-6048-4e82-855d-d7ed5ec24260)

---

## J-Type Instruction Format

| **Bit**  | 31         | 30-21     | 20        | 19-12      |  11-7     |  6-0      |
|----------|------------|-----------|-----------|------------|-----------|-----------|
| **Field**| imm[20]    | imm[10:1] |  imm[11]  | imm[19:12] | rd        | opcode    |
| **Description** | Immediate bit [20] | Immediate bits [10:1] |Immediate bit [11] |Immediate bits [19:12] | Destination Register | Operation code |

![WhatsApp Image 2024-12-06 at 17 54 28_19a3ba51](https://github.com/user-attachments/assets/7a90011d-b24e-452c-9063-2a1d51181c5d)

---


## Encoding Branch Prediction Using a Neural Network Application Instructions

### **1. addi sp, sp, -496**

For the instruction `addi sp, sp, -496`:

| **Bit**       | **31-20**       | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|
| **Field**     | imm[11:0]       | rs1 (sp)  | funct3    | rd (sp)   | opcode    |
| **Value**     | 111111111000    | 00010     | 000       | 00010     | 0010011   |


---

### **2. sd ra, 488(sp)**

For the instruction `sd ra, 488(sp)`:

| **Bit**       | **31-25**       | **24-20** | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|-----------|
| **Field**     | imm[11:5]       | rs2 (ra)  | rs1 (sp)  | funct3    | imm[4:0]  | opcode    |
| **Value**     | 0111100         | 00001     | 00010     | 011       | 01000     | 0100011   |

---

### **3. sd s0, 480(sp)**

For the instruction `sd s0, 480(sp)`:

| **Bit**       | **31-25**       | **24-20** | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|-----------|
| **Field**     | imm[11:5]       | rs2 (s0)  | rs1 (sp)  | funct3    | imm[4:0]  | opcode    |
| **Value**     | 0111000         | 00000     | 00010     | 011       | 00000     | 0100011   |


---

### **4. sd s1, 472(sp)**

For the instruction `sd s1, 472(sp)`:

| **Bit**       | **31-25**       | **24-20** | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|-----------|
| **Field**     | imm[11:5]       | rs2 (s1)  | rs1 (sp)  | funct3    | imm[4:0]  | opcode    |
| **Value**     | 0111000         | 00001     | 00010     | 011       | 00000     | 0100011   |

---

### **5. sd s2, 464(sp)**

For the instruction `sd s2, 464(sp)`:

| **Bit**       | **31-25**       | **24-20** | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|-----------|
| **Field**     | imm[11:5]       | rs2 (s2)  | rs1 (sp)  | funct3    | imm[4:0]  | opcode    |
| **Value**     | 0111000         | 00010     | 00010     | 011       | 00000     | 0100011   |

---

### **6. sd s3, 456(sp)**

For the instruction `sd s3, 456(sp)`:

| **Bit**       | **31-25**       | **24-20** | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|-----------|
| **Field**     | imm[11:5]       | rs2 (s3)  | rs1 (sp)  | funct3    | imm[4:0]  | opcode    |
| **Value**     | 0111000         | 00011     | 00010     | 011       | 00000     | 0100011   |

---

### **7. addi a3, sp, 272**

For the instruction `addi a3, sp, 272`:

| **Bit**       | **31-20**       | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|
| **Field**     | imm[31:20]      | rs1 (sp)  | funct3    | rd (a3)   | opcode    |
| **Value**     | 000000010000     | 00010     | 000       | 01100     | 0010011   |

---

### **8. addi a2, sp, 280**

For the instruction `addi a2, sp, 280`:

| **Bit**       | **31-20**       | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|
| **Field**     | imm[31:20]      | rs1 (sp)  | funct3    | rd (a2)   | opcode    |
| **Value**     | 000000010100     | 00010     | 000       | 01010     | 0010011   |

---

### **9. addi a1, sp, 304**

For the instruction `addi a1, sp, 304`:

| **Bit**       | **31-20**       | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|
| **Field**     | imm[31:20]      | rs1 (sp)  | funct3    | rd (a1)   | opcode    |
| **Value**     | 000000010110     | 00010     | 000       | 01001     | 0010011   |

---

### **10. addi a0, sp, 328**

For the instruction `addi a0, sp, 328`:

| **Bit**       | **31-20**       | **19-15** | **14-12** | **11-7**  | **6-0**   |
|---------------|-----------------|-----------|-----------|-----------|-----------|
| **Field**     | imm[31:20]      | rs1 (sp)  | funct3    | rd (a0)   | opcode    |
| **Value**     | 000000011000     | 00010     | 000       | 01010     | 0010011   |

---

### **11. jal ra, 10284 <initialize>**

For the instruction `jal ra, 10284 <initialize>`:

| **Bit**       | **31**   | **30-21**     | **20**   | **19-12**     | **11-7** | **6-0**   |
|---------------|----------|---------------|----------|---------------|----------|-----------|
| **Field**     | imm[20]  | imm[10:1]     | imm[11]  | imm[19:12]    | rd (ra)  | opcode    |
| **Value**     | 0        | 0000001011    | 1        | 000010010100  | 00000    | 1101111   |

---

### **12. lui a5, 0x22**

For the instruction `lui a5, 0x22`:

| **Bit**       | **31-12**   | **11-7**   | **6-0**   |
|---------------|-------------|------------|-----------|
| **Field**     | imm[31:12]  | rd (a5)    | opcode    |
| **Value**     | 000000000010 | 00101      | 0110111   |

---

### **13. addi a5, a5, 960**

For the instruction `addi a5, a5, 960`:

| **Bit**       | **31-20**      | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:20]     | rs1 (a5)  | funct3    | rd (a5)  | opcode    |
| **Value**     | 000000111100    | 00101     | 000       | 00101    | 0010011   |

---

### **14. addi a4, sp, 80**

For the instruction `addi a4, sp, 80`:

| **Bit**       | **31-20**      | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:20]     | rs1 (sp)  | funct3    | rd (a4)  | opcode    |
| **Value**     | 000000001010    | 00010     | 000       | 00100    | 0010011   |

---

### **15. addi a6, a5, 160**

For the instruction `addi a6, a5, 160`:

| **Bit**       | **31-20**      | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:20]     | rs1 (a5)  | funct3    | rd (a6)  | opcode    |
| **Value**     | 000000010100    | 00101     | 000       | 00110    | 0010011   |

---

### **16. ld a0, 0(a5)**

For the instruction `ld a0, 0(a5)`:

| **Bit**       | **31-20**      | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:20]     | rs1 (a5)  | funct3    | rd (a0)  | opcode    |
| **Value**     | 000000000000    | 00101     | 010       | 00000    | 0000011   |


---

### **17. ld a1, 8(a5)**

For the instruction `ld a1, 8(a5)`:

| **Bit**       | **31-20**      | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:20]     | rs1 (a5)  | funct3    | rd (a1)  | opcode    |
| **Value**     | 000000000010    | 00101     | 010       | 00001    | 0000011   |

---

### **18. ld a2, 16(a5)**

For the instruction `ld a2, 16(a5)`:

| **Bit**       | **31-20**      | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:20]     | rs1 (a5)  | funct3    | rd (a2)  | opcode    |
| **Value**     | 000000000100    | 00101     | 010       | 00010    | 0000011   |

---

### **19. ld a3, 24(a5)**

For the instruction `ld a3, 24(a5)`:

| **Bit**       | **31-20**      | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:20]     | rs1 (a5)  | funct3    | rd (a3)  | opcode    |
| **Value**     | 000000000110    | 00101     | 010       | 00011    | 0000011   |


---

### **20. sd a0, 0(a4)**

For the instruction `sd a0, 0(a4)`:

| **Bit**       | **31-25**      | **24-20** | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:25]     | rs2 (a0)  | rs1 (a4)  | funct3    | imm[4:0] | opcode    |
| **Value**     | 0000000        | 00000     | 00100     | 011       | 00000    | 0100011   |

---


### **21. sd a1, 8(a4)**

For the instruction `sd a1, 8(a4)`:

| **Bit**       | **31-25**      | **24-20** | **19-15** | **14-12** | **11-7** | **6-0**   |
|---------------|----------------|-----------|-----------|-----------|----------|-----------|
| **Field**     | imm[31:25]     | rs2 (a1)  | rs1 (a4)  | funct3    | imm[4:0] | opcode    |
| **Value**     | 0000000        | 00011     | 00100     | 011       | 01000    | 0100011   |

---
</details>
<details>
<summary><b>Task 4:</b> RISC-V Core Verilog netlist and testbench for functional simulation experiment </summary>   
<br>

## 1. RISC-V RV32I

This project provides an insight into the working of a few important instructions of the instruction set of a Single cycle Reduced Instruction Set Computer - Five(RISC-V) Instruction Set Architecture suitable for use across wide-spectrum of Applications from low power embedded devices to high performance Cloud based Server processors. The base RISC-V is a 32-bit processor with 31 general-purpose registers, so all the instructions are 32-bit long. Some Applications where the RISC-V processors have begun to make some significant threads are in Artificial intelligence and machine learning, Embedded systems, Ultra Low power processing systems etc.

## 2. BLOCK DIAGRAM OF RISC-V RV32I
![image](https://user-images.githubusercontent.com/110079631/181293948-beb8622c-7696-4b06-b6c9-eeab9b8ab9d3.png)

## 3. INSTRUCTION SET OF RISC-V RV32I
![image](https://user-images.githubusercontent.com/110079631/181298133-60269bc2-01da-4b5c-8b42-69057b8dc15c.png)

## 4. FUNCTIONAL SIMULATION

### 4.1 About iverilog and gtkwave
- Icarus Verilog is an implementation of the Verilog hardware description language.
- GTKWave is a fully featured GTK+ v1. 2 based wave viewer for Unix and Win32 which reads Ver Structural Verilog Compiler generated AET files as well as standard Verilog VCD/EVCD files and allows their viewing.

### 4.2 Installing iverilog and gtkwave

- **For Ubuntu**

 Open your terminal and type the following to install iverilog and GTKWave
 ```
 $   sudo apt get update
 $   sudo apt get install iverilog gtkwave
 ```

- **To clone the repository and download the netlist files for simulation , enter the following commands in your terminal.**

 ```
 $ git clone https://github.com/vinayrayapati/iiitb_rv32i
 $ cd iiitb_rv32i
 ```
- **To simulate and run the verilog code , enter the following commands in your terminal.**

```
$ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
$ ./iiitb_rv32i
```
- **To see the output waveform in gtkwave, enter the following commands in your terminal.**

`$ gtkwave iiitb_rv32i.vcd`

### 4.3 The output waveform
</details>
