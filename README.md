# VSD_RISK V_internship
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































