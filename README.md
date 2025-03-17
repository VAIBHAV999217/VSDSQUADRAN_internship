# VSD_RISC V_internship
1-month Research Internship on VSD Squadron Mini based on RISC-V, the board is powered by a CH32V003F4U6 chip with a 32-bit RISC-V core.
 
 Intern Name # Vaibhav Revankar #
 
 College # SJB INSTITUTE OF TECHNOLOGY #
 
 Course Instructor # Kunal Ghosh #
 This VSDSquadron Mini-Internship program introduces participants to the world of VLSI chip design and RISC-V architecture using open-source tools. It provides a practical, hands-on learning experience centered around the VSDSquadron Mini RISC-V Development Board.The development board is equipped with a 32-bit RISC-V core, 16KB of flash memory, and 2KB of SRAM, operating at a clock speed of 24MHz. It features 15 GPIO pins for hardware interfacing and supports widely-used communication protocols such as I2C, SPI, and USART, making it versatile for a range of projects. These capabilities allow participants to build and prototype hardware applications while deepening their understanding of the RISC-V ecosystem.
<details>
<summary><b>Introducing VSDSquadron Mini Board</b></summary> 
 
![boards](https://github.com/user-attachments/assets/35cb219a-d315-4cd6-8eb3-f142dde7c905)

This is the Link,Which directs to the Datasheet of the VSDsquadran mini board.

 ```
 [DataSheet](https://www.vlsisystemdesign.com/wp-content/uploads/2024/01/VSDSQMinidatasheet.pdf)
 ```
</details>
<details>
<summary><b>Task 1:</b> Installing RISC-V toolchain and Refer to C and RISC-V based lab videos </summary>   
<br>

## 1. C-Based Activities
The installation of the ubuntu is done successfully.
 
![task1_in ubuntu](https://github.com/user-attachments/assets/b58de310-1570-4bd4-aee6-19f33308eaae)

Open terminal inside Ubuntu,Now Install leafpad editor for C programming using command

 ```
         sudo apt  install leafpad
 ```
After Installing leafpad, create a file to write a simple code to calculate sum of 1 to n.

![task1_c_programming](https://github.com/user-attachments/assets/6917993c-f059-451c-bf82-d62cec17a26c)

Run the program and check the results using commands
 ````
gcc sum1ton.c
./a.out 
````
result :

![task1_results](https://github.com/user-attachments/assets/498aac41-0006-4d33-991c-06e9cc41a158)

## 2.RISC Based Activities
Compile the C code using the RISC V Processor, and check the output

 the below command compiles the c program using risc v compiler
  
    riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o 1ton.o 1ton.c

![task1_Ofast](https://github.com/user-attachments/assets/5d12de7a-d7f7-40b2-bde1-ec5e8cdda08b)
    
![task1_after_Ofast](https://github.com/user-attachments/assets/fed7df70-ab28-49ce-9126-c6b0ad78d70e)

  This command generates an assembly code for the program

    riscv64-unknown-elf-objdump -d 1ton.o | less
    
Observations in Assembly Instructions

          The byte address for the main was found to be 10184.
          There were 15 instructions (in hexadecimal: E) when compiled with the -O1 optimization level.
          The address of each consecutive instruction increments by 4 bytes, as observed in the disassembled output.
          
The same commands were run with the -Ofast optimization level instead of -O1, resulting in a reduced number of instructions—12.

     o This demonstrates that the number and type of assembly instructions generated depend on the compilation optimization level used.
     o The higher optimization (-Ofast) produces a more compact and efficient assembly.

![task1_riscv2](https://github.com/user-attachments/assets/3d3f7c24-c279-423f-b772-179951334489)
![task1_riscv3](https://github.com/user-attachments/assets/53f1aa31-cd9d-43e8-83bc-cf54359fc056)

now we have to locate the main section

    /main

![task1_riscv4 (1)](https://github.com/user-attachments/assets/ff64442d-021b-42bc-b761-e12d6ce6354c)

</details>

<details>
<summary><b>Task 2:</b> SPIKE Simulation </summary> 
Write a C code to find the lcm of 2 numbers. Compile it using the RISC compiler and simulate it using the spike simulation. Observe the -o1 and -ofast response and debug the assembly level code using spike

## 1. Simple C Program to find LCM of 2 numbers
![taks2_spike1](https://github.com/user-attachments/assets/2c7c1b3f-6e42-458c-addb-4be099c28e78)

## 2. Running the code using GCC and compile it using the risc-v compiler and simulate the output using the SPIKE
the below command is used to run to spike simulation

    spike -d pk lcm.o
![task2_spike2](https://github.com/user-attachments/assets/7765529d-c4e6-4200-b145-877bbaa01952)
## 3. Observe the -o1 and -0fast instruction response using the RISC-V gcc/ SPIKE
-o1 assembly Code
![task1_Ofast](https://github.com/user-attachments/assets/5d12de7a-d7f7-40b2-bde1-ec5e8cdda08b)

-ofast assembly Code
![task1_after_Ofast](https://github.com/user-attachments/assets/fed7df70-ab28-49ce-9126-c6b0ad78d70e)

## 4. Debug the code by using the spike instruction

The below command is used to debug the assembly code using the SPIKE

    spike -d pk lcm.o

![task2_spike3](https://github.com/user-attachments/assets/b9ab2118-b72f-4351-8cb4-1f970a38fdd6)

![task2_spike4](https://github.com/user-attachments/assets/552fead6-d788-4784-83da-d19715c41022)

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
![task4_install iveriloggtkwave](https://github.com/user-attachments/assets/fefa5740-3aa5-48f9-8339-95b505e40c0e)

- **To clone the repository and download the netlist files for simulation , enter the following commands in your terminal.**

 ```
 $ git clone https://github.com/vinayrayapati/iiitb_rv32i
 $ cd iiitb_rv32i
 ```
- **To simulate and run the verilog code , enter the following commands in your terminal.**
Now Type the following command to create a file in the system ,where verilog ang and systemverilog code need to be saved.

 ```
mkdir vaibhav03
mkdir vaibhav03_testbench
 ```

![task4_1](https://github.com/user-attachments/assets/3472751f-16d8-497f-a5a8-8fce5d1f99e5)

- **This is where the files are been created and saved in the system.**
  
![task4_2](https://github.com/user-attachments/assets/73aba8af-e689-443f-80eb-da4057a6eff8)
![task4_3](https://github.com/user-attachments/assets/bcfa059c-2ebf-4bf8-b7a3-6aa76214d781)

- **Verilog Code**

![task4_verilogcode](https://github.com/user-attachments/assets/daafa520-03e0-497e-b3c7-54d7bf865674)
- **Testbench Code**
  
![task4_testbenchcode](https://github.com/user-attachments/assets/59a42ba9-067c-4950-8534-76f616804a9e)

- **Output Just before simulating the Waveform**
  
![task4_4](https://github.com/user-attachments/assets/d590220f-73da-4c9a-9cf2-ca4a475f2e97)

![task4_5](https://github.com/user-attachments/assets/fc6e3865-8935-4415-9c40-8b5fd95cb19d)

- **Waveform**

![task4_waveform](https://github.com/user-attachments/assets/3aa3becc-ccb4-44a9-8871-5786f3d6cc83)

</details>
<details>
<summary><b>Task 5:</b>FinalProject</summary>   
<br>

# Alert System Using Ultrasonic Sensor

## Project Overview
The "Alert System Using Ultrasonic Sensor" is a project designed to detect nearby objects and provide a visual alert through an LED indicator. This system utilizes an ultrasonic sensor to measure the distance to an object and activates the LED when the object is within a specified threshold distance. This project can be applied in various scenarios, such as obstacle detection in robotics, water level monitoring, and safety systems.

## Features
- **Object Detection**: Measures the distance to nearby objects using an ultrasonic sensor.
- **Visual Alert**: Activates an LED indicator when an object is detected within a specified distance.
- **Real-time Monitoring**: Continuously monitors the environment and updates the alert status based on distance measurements.

## Hardware Components
- **Microcontroller**: CH32V00x (or any compatible microcontroller)
- **Ultrasonic Sensor**: HC-SR04 or similar
- **LED**: For visual alert
- **Resistors**: (if needed for LED)
- **Jumper Wires**
- **Breadboard**: (optional for prototyping)

## Software Requirements
- **PlatformIO**: PlatformIO is an open-source ecosystem for IoT development that integrates seamlessly with Visual Studio Code, providing a powerful environment for building, debugging, and managing embedded projects across various platforms frameworks and programming the microcontroller .
- **Libraries**: Standard libraries for GPIO and delay functions

|        **Comopents**           |  **Pin**  | **Microcontroller Pin** |                       **Description**                           | 
|--------------------------------|-----------|-------------------------|-----------------------------------------------------------------|
| **Ultrasonic Sensor Trigger**  | Pin 4     | GPIOD Pin 4             | Sends trigger pulse to the ultrasonic sensor.                   | 
| **Ultrasonic Sensor Echo**     | Pin 3     | GPIOD Pin 3             | Receives echo signal from the ultrasonic sensor.                |
| **LED Indicator**              | Pin 6     | GPIOD Pin 6             | Visual alert indicator that turns on when an object is detected.|

## Circuit Diagram
![Screenshot 2025-03-17 160211](https://github.com/user-attachments/assets/eedd62bf-8d41-4001-bab5-11e5084a1916)

## Project Code

#include <ch32v00x.h>
#include <debug.h>

/* Threshold distance in cm for object detection */
#define OBJECT_DETECTION_THRESHOLD 10

/* Function to configure GPIO Pins */
void GPIO_Config(void)
{
    GPIO_InitTypeDef GPIO_InitStructure = {0};

    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE);

    // Pin 3: Input for Ultrasonic sensor echo
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_3;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU; // Input with Pull-Up
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Pin 4: Output for Ultrasonic sensor trigger
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_4;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP; // Output Push-Pull
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Pin 6: LED indicator
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_6;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP; // Output Push-Pull
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);
}

/* Function to trigger the ultrasonic sensor and read the echo duration */
uint32_t Ultrasonic_Read(void)
{
    uint32_t echoTime = 0;

    GPIO_WriteBit(GPIOD, GPIO_Pin_4, SET); // Setting Trigger Pin to send pulses
    Delay_Us(10); // Pulse Width
    GPIO_WriteBit(GPIOD, GPIO_Pin_4, RESET); // Resetting Trigger Pin

    while (GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_3) == Bit_RESET); // Wait for Echo to go high
    while (GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_3) == Bit_SET) echoTime++; // Measure the time Echo is high

    return echoTime;
}

/* Function to calculate distance from echo time */
float Calculate_Distance(uint32_t echoTime)
{
    // Speed of sound in air is 340 m/s or 0.034 cm/us
    // Distance is (time / 2) * speed_of_sound
    return (echoTime / 2.0) * 0.034;
}

/* Main function */
int main(void)
{
    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);
    SystemCoreClockUpdate();
    Delay_Init();
    GPIO_Config();
    USART_Printf_Init(115200); // Initialize debug USART

    while (1)
    {
        uint32_t echoTime = Ultrasonic_Read();
        float distance = Calculate_Distance(echoTime);

        printf("Distance: %.2f cm\n", distance); // Print the distance

        if (distance < OBJECT_DETECTION_THRESHOLD) // If an object is detected within the threshold
        {
            GPIO_WriteBit(GPIOD, GPIO_Pin_6, Bit_SET); // Turn on LED
        }
        else
        {
            GPIO_WriteBit(GPIOD, GPIO_Pin_6, Bit_RESET); // Turn off LED
        }

        Delay_Ms(100); // Wait for a short time before the next reading
    }
}


Conclusion and 
Add Link

</details>































































