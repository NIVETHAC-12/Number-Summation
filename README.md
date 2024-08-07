# Vsdsquadron-mini-Internship
**Description:**
The VSDQuadron Mini Internship offers a hands-on experience focused on developing and working with a state-of-the-art development board. This internship is designed for aspiring engineers and developers who are keen to delve into the world of embedded systems and hardware design. Participants will gain practical knowledge and experience in programming, interfacing, and utilizing various features of the VSDQuadron development board.

**Development Board Features:**
* **32-bit RISC-V Core:** 
 The heart of the VSDQuadron development board is a powerful 32-bit RISC-V processor. This open-source instruction set architecture (ISA) is known for its flexibility and scalability, making it an excellent choice for educational and development purposes.
* **Multiple Clock Options:** 
 The board provides various clock configurations, allowing participants to explore different operational frequencies and power modes. This feature is crucial for optimizing performance and energy consumption in embedded applications.
* **15 GPIO Pins:** 
 The board is equipped with 15 General Purpose Input/Output (GPIO) pins. These versatile pins can be programmed for various functions, including digital input, digital output, and more. They are essential for interfacing with external sensors, actuators, and other peripherals.

## TASK 1  **Sum of Numbers 1 to N**
* Install the RISC-V toolchain using VDI
* Use the Terminal Windows in UBUNTU
* C code for sum of numbers from 1 to N

**1. Virtual box Installed**

![Virtual box installation](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/641679b3-60fc-409f-990a-c536e7f88f5b)


**2. Ubuntu Installed**

![Installation of Ubuntu](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/acca4611-8085-4230-8e61-70a1c0059c9d)


**3. C code to execute The Sum of Numbers 1 to N**

  * Leafpad id installed using `sudo snap install leafpad`
   
  * Create fine using `leafpad sum1ton.c &`
   
  * Here you fnd the leafpad to code `write the code`

    
![C Program for Sum of 1 to N](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/cd115830-5786-4517-a151-69c5e15d5114)


**4.Output for the C Program**

* Compile the program using `gcc sum1ton.c`
 
* Execute the program using `./a.out`
  

![Fast Instruction](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/42149cdb-44a3-4269-8b6d-ee254ecbaee4)


**5.C program to RISC-V instruction Set**

* *command 1* `riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c`
 
* Switch tab *command 2*   ` riscv64-unknown-elf-objdump -d sum1ton.o| less` and access the main part using main function `/main`

* To calculate the different execution with _Ofast_ instead of _O1_ as `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c`
  

   ![Fast Instruction](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/d4ee1ad1-7ae1-445f-aaad-ee2c135bd4ba)
  

  ![Main Function](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/48eefbd7-a55e-4a1f-846a-ce2cb498a1c0)



**6.Calculation RISC-V instruction**


![Calculation of riscv instruction](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/5e74773d-9233-4503-b863-695b4bd37a16)


## Conclusion

 By following these steps, you will have a virtual environment set up with the RISC-V toolchain ready for development. This setup allows you to compile and test RISC-V programs.

  
  **XXXXXXXXXX**


## Task 2
 
  ## PROJECT 1 - Ticket Terminal Designer: Developing an Automated Parking Ticket Vending Machine

  The provided C program is a simple implementation of an Automated Parking Ticket Vending Machine. The program offers functionalities to issue parking tickets, process payments for the issued tickets, and provides a user interface through a console menu.

  ## 1 CODE 

  **LANGUAGE C**
  
```
#include <stdio.h>
#include <stdlib.h>

int current_ticket = 0;

void issue_ticket() {
    current_ticket++;
    printf("Ticket issued: %d\n", current_ticket);
}

void pay_ticket(int ticket_number) {
    if (ticket_number <= current_ticket && ticket_number > 0) {
        printf("Ticket %d has been paid.\n", ticket_number);
    } else {
        printf("Invalid ticket number.\n");
    }
}

void show_menu() {
    printf("1. Issue Ticket\n");
    printf("2. Pay Ticket\n");
    printf("3. Exit\n");
}

int main() {
    int choice, ticket_number;

    while (1) {
        show_menu();
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                issue_ticket();
                break;
            case 2:
                printf("Enter ticket number to pay: ");
                scanf("%d", &ticket_number);
                pay_ticket(ticket_number);
                break;
            case 3:
                exit(0);
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}
```


## CODE BREAKDOWN :

 **1.Global Variable:**

  *  `int current_ticket = 0;`
    
  * This variable keeps track of the total number of tickets issued.

    
**2.Functions:**


`void issue_ticket()`

* This function increments the `current_ticket` counter and prints a message indicating that a new ticket has been issued along with the ticket number.
  
*  **Behavior:** Each time this function is called, it simulates issuing a new parking ticket by incrementing 
      the ticket count.
  
*
```
   
  void issue_ticket() {
    current_ticket++;
    printf("Ticket issued: %d\n", current_ticket);
  }
 ```


* `void show_menu()`
  
* This function prints the main menu options to the console.
  
* **Behavior:** Provides a user-friendly interface for interacting with the program.
  

```
void show_menu() {
    printf("1. Issue Ticket\n");
    printf("2. Pay Ticket\n");
    printf("3. Exit\n");
}
```


**3.Main Function:**

* The main function runs an infinite loop to keep the program active until the user decides to exit.
  
* Inside the loop, it displays the menu using `show_menu()` , reads the user's choice, and executes the corresponding action using a switch-case structure.
  
* *CASE 1:* Calls `issue_ticket()` to issue a new ticket.
  
* *CASE 2:* Prompts the user to enter a ticket number and calls `pay_ticket()` to process the payment.
  
* *CASE 3:* Exits the program.
  
* *Default Case:* Handles invalid menu choices by printing an error message.
  
*Behavior:* Manages the flow of the program and user interactions.


```
int main() {
    int choice, ticket_number;

    while (1) {
        show_menu();
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                issue_ticket();
                break;
            case 2:
                printf("Enter ticket number to pay: ");
                scanf("%d", &ticket_number);
                pay_ticket(ticket_number);
                break;
            case 3:
                exit(0);
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}
```
 
 
## **Summary:**

* The program provides a basic implementation of a parking ticket vending system.

* Users can issue new tickets and pay for existing tickets through a simple menu interface.
  
* The `current_ticket` variable keeps track of the number of issued tickets.
 
*The program continuously runs, allowing users to interact until they choose to exit.

This code serves as a foundational example of how an automated ticket vending system can be implemented in C. It can be further extended with additional features such as ticket validation, payment processing, and database integration for a more robust solution.


![Screenshot from 2024-06-25 16-06-29](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/b60c264e-baf7-46e0-b955-2c7713e5e0d7)


![Screenshot from 2024-06-25 12-39-04](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/d894a1b2-ca5f-4074-996b-87703f7d6cfa)

 ### 2 OUTPUT

 * Compile the program using `gcc ticketterminal.c` and execute the program using `./a.out` command
   

 ![Screenshot from 2024-06-25 16-21-39](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/204cc40b-8da0-4e3d-98ff-0723164110f4)


 ## 3 Converting the C program to RISC-V instruction set 

 * Compile the code using the RISC-V GCC compiler with the following command:
  
   ```
   riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c
   ```

![Screenshot from 2024-06-25 16-35-56](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/ce9bdc2a-61c4-4661-bd88-092bfd94c4c5)

* Now, switch tab to function your main function and calculation using this command :

```
riscv64-unknown-elf-objdump -d ticketterminal.o |less
```

 ![Screenshot from 2024-06-25 17-10-05](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/37e0ac71-1e04-46f1-b54b-f54eebaf0e41)

 * To access the main function using `/main` statement

![Screenshot from 2024-06-25 17-17-07](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/90504dbc-bf82-4f48-bc8c-cfa3fc62695d)


* calculation for `-o1` instruction

![Screenshot 2024-06-25 125814](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/a70225a9-0607-410b-b848-35c76096b0ee)

* So here in the above calculation there are **43** lines in the main function

* To obtain the difference execute the same function using the `-Ofast` function like given below

   `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`

![Screenshot from 2024-06-25 16-35-56 (1)](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/74a5dcad-e963-404d-8ef5-ef1985a5996a)

* Same way,access the main function again to calculate the number of instructions

![Screenshot 2024-06-25 131849](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/94b40382-1128-48cd-9c7d-f550f918e90f)


* There are 14 lines in the instruction in the main block of the function `Ofast` by comparing both the main functions we come to know that the `Ofast` function has been reduced for few numbers.

## CONCLUSION


The provided C program effectively demonstrates the fundamental operations of an Automated Parking Ticket Vending Machine. By utilizing simple functions and a console-based menu interface, the code provides a clear and accessible way to issue parking tickets and process their payments.

           
           
   **XXXXXXXXXX**




   ## TASK 3

   ### SPIKE simulation and verification with -O1 and -OFast along with running the RISK-V Objdump.


**1.Simulation with SPIKE:**

* Perform a simulation of your RISC-V program using the SPIKE RISC-V ISA simulator.


**2.Verification with Optimization Levels:**

* Verify the program's behavior with two different levels of optimization:

 
 * `-O1`: This optimization level enables basic optimizations that improve performance without significantly increasing 
         compilation time.
 
 * `-Ofast`: This level enables aggressive optimizations, potentially breaking strict standards compliance for maximum 
           performance.


**3.Running RISC-V objdump:**

* Use the RISC-V objdump tool to disassemble the program's binary, providing a human-readable assembly representation of the 
  machine code.


  ## So, here is all put together,you want to:

  **1.Simulate your RISC-V program using the SPIKE simulator.*
  
  **2.Verify the program's performance and correctness with two different optimization levels (-O1 and -Ofast).*

  **Use the RISC-V `objdump` tool to disassemble and inspect the binary.



## Here are the possible sequence of steps:

   **1.Compile the program with different optimization levels:**

```
riscv64-unknown-elf-gcc -O1 -o program_O1 program.c
riscv64-unknown-elf-gcc -Ofast -o program_Ofast program.c
```


![Screenshot from 2024-06-27 11-28-13](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/bde8e7c1-31a5-4f79-aa35-51742a82f652)


( Here we 1st got the output for our c program which we got from the AI tool)

(**DeBUG done here**) command:

* `riscv64-unknown-elf-objdump -d ticketterminal.o |less` 


![Screenshot from 2024-06-27 11-28-34](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/2c5e0e53-2f83-4277-b1c6-f18c7285c663)




 **2.Spike simulation:**

 * command :

     `spike pk ticketterminal.o`


 
 ![Screenshot from 2024-06-27 11-27-57](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/34ee901f-3d74-4968-8218-6e81e8c4a705)



**3.Disassemble the binaries with `objdump`:**


* To debug the spike we need this command `spike -d pk ticketterminal.o`


* Then, by using the command `until pc 0 100b0`,which is the 1st line command of the main function the program counter runs from the 0 till the code 100b0


* To find the contents of the code we need to use the command `reg 0 sp` in which we content of the `100b0` th line


* To find the content in the next line just give `ENTER`


* Initially the value of the sp is `0X0000003ffffffb40` then the next step the sp values get subtracted with the hexadecimal and we get `0X0000003ffffffac0`


* Finally, by subtracting the both main function values we get the 3rd output as `0X000000ffffffac0`




![Screenshot from 2024-06-27 11-31-02](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/4ed1f888-889d-4749-a9d9-ca6bb09ed7a5)


XXXXXXXXXX



# TASK 4


## Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions 
**ADD r1, r2, r3*
**SUB r3, r1, r2*
**AND r2, r1, r3*
**OR r8, r2, r5*
**XOR r8, r1, r4*
**SLT r10, r2, r4*
**ADDI r12, r3, 5*
**SW r3, r1, 4*
**SRL r16, r11, r2*
**BNE r0, r1, 20*
**BEQ r0, r0, 15*
**LW r13, r11, 2*
**SLL r15, r11, r2*
Upload the 32-bit pattern on Github 





**RISC-V, an open standard instruction set architecture (ISA), categorizes its instructions into several types based on their formats and intended operations. The primary RISC-V instruction types are R, I, S, B, U, and J.**



**1. R-Type (Register Type)**
R-Type instructions are used for arithmetic and logical operations where all operands are registers.



**2. I-Type (Immediate Type)**
I-Type instructions are used for operations involving an immediate value (a constant) and a register.  

 
   
**3. S-Type (Store Type)**
S-Type instructions are used for store operations, where data from a register is stored into memory.



**4. B-Type (Branch Type)**
B-Type instructions are used for conditional branch operations, changing the flow of control based on a comparison.



**5. U-Type (Upper Immediate Type)**
U-Type instructions are used for operations involving a 20-bit upper immediate value.


  
**6. J-Type (Jump Type)**
J-Type instructions are used for jump operations, changing the flow of control unconditionally.



**Here’s an overview of each type:**


# R-TYPE INSTRUCTION


**R-Type instructions format: `funct7 | rs2 | rs1 | funct3 | rd | opcode`**

* 1.ADD r1,r2,r3


   * opcode: `0110011` (R-type)
   * funct3: `000`
   * funct7: `0000000`
   * rs1: `r2` (010)
   * rs2: `r3` (011)
   * rd: `r1` (001)
   * 32-bit: `0000000 011 010 000 001 0110011`



* 2.SUB r3,r1,r2


    * opcode: `0110011` (R-type)
    * funct3: `000`
    * funct7: `0100000`
    * rs1: `r1` (001)
    * rs2: `r2` (010)
    * rd: `r3` (011)
    * 32-bit: `0100000 010 001 000 011 0110011`



* 3.AND r2, r1, r3


   * opcode: `0110011` (R-type)
   * funct3: `111`
   * funct7: `0000000`
   * rs1: `r1` (001)
   * rs2: `r3` (011)
   * rd: `r2` (010)
   * 32-bit: `0000000 011 001 111 010 0110011`

   

* 4.OR r8,r2,r5


   * opcode: `0110011` (R-type)
   * funct3: `110`
   * funct7: `0000000`
   * rs1: `r2` (010)
   * rs2: `r5` (101)
   * rd: `r8` (1000)
   * 32-bit: `0000000 101 010 110 1000 0110011`



* 5.XOR r8,r1,r4


   * opcode: `0110011` (R-type)
   * funct3: `100`
   * funct7: `0000000`
   * rs1: `r1` (001)
   * rs2: `r4` (100)
   * rd: `r8` (1000)
   * 32-bit: `0000000 100 001 100 1000 0110011`



* 6.SLT r10,r2,r4


   * opcode: `0110011` (R-type)
   * funct3: `010`
   * funct7: `0000000`
   * rs1: `r2` (010)
   * rs2: `r4` (100)
   * rd: `r10` (1010)
   * 32-bit: `0000000 100 010 010 1010 0110011`



* 7.SRL r16,r11,r2


   * opcode: `0110011` (R-type)
   * funct3: `101`
   * funct7: `0000000`
   * rs1: `r11` (1011)
   * rs2: `r2` (010)
   * rd: `r16` (10000)
   * 32-bit: `0000000 010 1011 101 10000 0110011`



* 8.SLL r15,r11,r2


   * opcode: `0110011` (R-type)
   * funct3: `001`
   * funct7: `0000000`
   * rs1: `r11` (1011)
   * rs2: `r2` (010)
   * rd: `r15` (1111)
   * 32-bit: `0000000 010 1011 001 1111 0110011`



# I-TYPE INSTRUCTION 


**I-Type instructions format: `imm[11:0] | rs1 | funct3 | rd | opcode`**


* 9.ADDI r12,r3,5


  * opcode: `0010011` (I-type)
  * funct3: `000`
  * imm: `000000000101`
  * rs1: `r3` (011)
  * rd: `r12` (1100)
  * 32-bit: `000000000101 011 000 1100 0010011`



* 10.LW r13,r11,2


  * opcode: `0000011` (I-type)
  * funct3: `010`
  * imm: `000000000010`
  * rs1: `r11` (1011)
  * rd: `r13` (1101)
  * 32-bit: `000000000010 1011 010 1101 0000011`



# S-TYPE INSTRUCTIONS


**S-Type instructions format: `imm[11:5] | rs2 | rs1 | funct3 | imm[4:0] | opcode`**


* 11.SW r3,r1,4


  * opcode: `0100011` (S-type)
  * funct3: `010`
  * imm: `0000000 00100` (imm[11:5] = `0000000`, imm[4:0] = `00100`)
  * rs1: `r1` (001)
  * rs2: `r3` (011)
  * 32-bit: `0000000 011 001 010 00100 0100011`



# B-TYPE INSTRUCTION


**B-Type instructions format: `imm[12|10:5] | rs2 | rs1 | funct3 | imm[4:1|11] | opcode`**


* 12.BNE r0,r1,20


  * opcode: `1100011` (B-type)
  * funct3: `001`
  * imm: `0000000001010` (imm[12|10:5] = `000000`, imm[4:1|11] = `01010`)
  * rs1: `r0` (000)
  * rs2: `r1` (001)
  * 32-bit: `000000 001 000 001 01010 1100011`



* 13.BEQ r0,r0,15


   * opcode: `1100011` (B-type)
   * funct3: `000`
   * imm: `0000000000111` (imm[12|10:5] = `000000`, imm[4:1|11] = `01110`)
   * rs1: `r0` (000)
   * rs2: `r0` (000)
   * 32-bit: `000000 000 000 000 01110 1100011`




# U-TYPE INSTRUCTION


**There are no U-type instructions in the provided list.**


# J-TYPE INSTRUCTION


**There are no J-type instructions in the provided list.**



# Summary


**Here are the 32-bit patterns in order:**

* 1.ADD r1, r2, r3: 0000000 011 010 000 001 0110011
  
* 2.SUB r3, r1, r2: 0100000 010 001 000 011 0110011
  
* 3.AND r2, r1, r3: 0000000 011 001 111 010 0110011
  
* 4.OR r8, r2, r5: 0000000 101 010 110 1000 011001
  
* 5.XOR r8, r1, r4: 0000000 100 001 100 1000 0110011
  
* 6.SLT r10, r2, r4: 0000000 100 010 010 1010 0110011
  
* 7.SRL r16, r11, r2: 0000000 010 1011 101 10000 0110011
  
* 8.SLL r15, r11, r2: 0000000 010 1011 001 1111 0110011

* 9.ADDI r12, r3, 5: 000000000101 011 000 1100 0010011
  
* 10.LW r13, r11, 2: 000000000010 1011 010 1101 0000011
  
* 11.SW r3, r1, 4: 0000000 011 001 010 00100 0100011
  
* 12.BNE r0, r1, 20: 000000 001 000 001 01010 1100011
  
* 13.BEQ r0, r0, 15: 000000 000 000 000 01110 1100011


XXXXXXXXXX




# TASK 5

## RISC-V Core Verilog netlist and Testbench for Functional simulation.


**Acknowledgements Section :**

   `https://github.com/vinayrayapati/rv32i/`
   
**I have developed a set of commands and achieved the desired output for my project. This was accomplished by referece above and the key sources, which provided valuable guidance and examples. These references were in understanding the required techniques and applying them effectively in my implementation.*


# REFERENCE-DRIVEN DEVELOPMENT


**WORKFLOW**

**1 .Cloning the Reference:**

* Cloning is the process of creating a local copy of a remote repository. This allows you to have a complete copy of the repo

* _Command 1_ : `git clone http://github.com/vinayrayapati/rv32i.git my_ticket_rv32i`


* _Command 2_ : `cd my_ticket_rv32i`


* ![Screenshot from 2024-07-08 12-27-00](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/bde0d41a-e8fb-44fc-b524-092f0b5cffbd)



* This will download the project into a local directory named `my_ticket_rv32i`.


**2 .Simulation Tools:**
  
* _command 3_ : `sudo apt update`

* _command 4_ : `sudo apt install inverilog gtkwave`


*![Screenshot from 2024-07-08 12-27-27](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/2e61f4d1-b02f-47e6-a40d-4055856bd23c)



![Screenshot from 2024-07-08 12-27-40](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/8328ecd5-3263-4283-bb87-2411441b406b)


**3 .Testbench File:**


  _Here we use the Testbench to setup our environment to test and validate code_


* Open Testbench file using text editor:

* `nano iiitb_rv32i_tb.v`


~~~
initial begin
RN = 1'b1;
clk = 1'b1;

$dumpfile ("iiitb_rv32i.vcd"); //by default vcd(NAME)
$dumpvars (0,iiitb_rv32i_tb);

   #5 RN = 1'b0;

   #300 $finish;
end
endmodule
~~~


![Screenshot from 2024-07-08 12-28-13](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/7456be8f-9258-49b2-9fae-b586fb89afce)


* Simulation

* `iverilog -o rv32i_simulation iiitb_rv32i.v iiitb_rv32i_tb.v`


![Screenshot from 2024-07-08 12-28-37 (1)](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/70c1d063-9c50-4be4-9075-415e25ba2e75)


**4 .Run Functional Simulation:**

* `vvp rv32i_simulation`


* ![Screenshot from 2024-07-08 11-50-20 (1)](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/ca54eba9-3a81-4e94-a386-040d41babc7e)


* Here we get he Output in the form of a wave

* `gtkwave simulation.vcd`

* Here we get the gtkwave windows and Output can be obtained.



# OUTPUT 

## 1.ADD (r1,r2,r3)

![addition git](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/d3041789-15f5-4bcb-b643-8333cc6e7e1d)


## 2.SUB (r3,r1,r2)

![sub github](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/efeafd91-16d0-453a-82a2-b176574577c1)


## 3. AND (r2,r1,r3)

![and git](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/f728b206-8c70-4801-a650-8e0e5f96e1cb)


## 4. OR (r8,r2,r5)


![OR GIT](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/9939ed4e-d827-492d-85dc-ca4a364bbe70)


## 5. XOR (r8,r1,r4)


![XOR GIT](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/fcdd12d6-5f2a-401e-9cda-0503aab1fae0)


## 6. SLT (r10,r2,r4)


![Screenshot from 2024-07-08 12-04-12](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/b78ca7fe-235f-48a4-8d9c-07bee64c9c16)


## 7. BEQ (r0,r0,15)


![BLQ GIT](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/28c48817-2cdc-4dfe-b224-8abbbc906ea3)


## 8. BNE (r0,r1,20)


![Screenshot from 2024-07-08 12-07-06 (1)](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/981af526-93f9-4bf2-8be5-c280853afe56)



## 9. SLL (r15,r11,r2)


![Screenshot from 2024-07-08 12-04-12](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/2645fe45-499c-42f8-93ca-d7adb01f1fa7)



## 10. GTKWAVE WINDOW


![Screenshot from 2024-07-08 11-52-07](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/d33352ef-8bf6-436e-ad5e-73e8f45f709b)


__TESTS EXECUTED AND RESULTS VERIFIED__


XXXXXXXXXX



# TASK 6

# AUTOMATED PARKING TICKET VENDING MACHINE 


## PROJECT OVERVIEW

   **OBJECTIVE**

   * Develop an automated parking ticket vending machine (PTVM) that can issue parking 
     tickets, accept payments, and provide receipts to users.

   **KEY FEATURES**

   * Ticket Issuance: Dispense parking tickets with relevant information.
  
   * Payment Processing: Accept cash, credit/debit cards, and digital payments.
  
   * Receipt Printing: Provide receipts for transactions.
  
   * User Interface: Simple and intuitive touch screen interface.
  
   * Backend System: Manage data and transactions.



## Hardware Components:


* _Microcontroller:_ Arduino, Raspberry Pi, or similar.

* _LCD Display:_ For showing information to the user.

* _Keypad:_ For user input.

* _Thermal Printer:_ For printing tickets and receipts.

* _Card Reader:_ For accepting credit/debit card payments.

* _Coin Acceptor and Bill Validator:_ For accepting cash payments.

* _RTC Module (Real-Time Clock):_ For keeping track of time.

* _Power Supply:_ To power all components.

* _LEDs and Buzzers:_ For status indicators and alerts.



## PIN DIAGRAM 


Let's assume we are using an Arduino Uno for simplicity. The connections might look something like this:

**1. LCD Display:**

1. VSS to GND

2. VDD to 5V

3. V0 to Potentiometer (for contrast control)

4. RS to Digital Pin 12

5. RW to GND

6. E to Digital Pin 11

7. D4 to Digital Pin 5

8. D5 to Digital Pin 4

9. D6 to Digital Pin 3

10. D7 to Digital Pin 2

11. A to 5V (Backlight Anode)

12. K to GND (Backlight Cathode)


## KEYPAD

* Connect the rows and columns of the keypad to Digital Pins (e.g., Pins 6, 7, 8, 9 for 
  rows and Pins 10, A0, A1, A2 for columns).

## RTC MODULE

* SDA to A4 (I2C Data)

* SCL to A5 (I2C Clock)

* VCC to 5V

* GND to GND

## LEDs AND BUZZERS 

* Connect LEDs to Digital Pins with appropriate current-limiting resistors.

* Connect Buzzer to a Digital Pin with a transistor if necessary.


## EXAMPLE PIN DIAGRAM 

```
+-------------------------+        +-------------------------+
|       Arduino Uno       |        |       Components        |
+-------------------------+        +-------------------------+
| LCD RS  -> Pin 12       |        | LCD RS -> Pin 12        |
| LCD E   -> Pin 11       |        | LCD E  -> Pin 11        |
| LCD D4  -> Pin 5        |        | LCD D4 -> Pin 5         |
| LCD D5  -> Pin 4        |        | LCD D5 -> Pin 4         |
| LCD D6  -> Pin 3        |        | LCD D6 -> Pin 3         |
| LCD D7  -> Pin 2        |        | LCD D7 -> Pin 2         |
| Keypad R1 -> Pin 6      |        | Keypad R1 -> Pin 6      |
| Keypad R2 -> Pin 7      |        | Keypad R2 -> Pin 7      |
| Keypad R3 -> Pin 8      |        | Keypad R3 -> Pin 8      |
| Keypad R4 -> Pin 9      |        | Keypad R4 -> Pin 9      |
| Keypad C1 -> Pin 10     |        | Keypad C1 -> Pin 10     |
| Keypad C2 -> Pin A0     |        | Keypad C2 -> Pin A0     |
| Keypad C3 -> Pin A1     |        | Keypad C3 -> Pin A1     |
| Keypad C4 -> Pin A2     |        | Keypad C4 -> Pin A2     |
| Printer TX -> Pin 9     |        | Printer TX -> Pin 9     |
| Printer RX -> Pin 10    |        | Printer RX -> Pin 10    |
| Coin Acceptor -> Pin 13 |        | Coin Acceptor -> Pin 13 |
| Bill Validator -> Pin A3|        | Bill Validator -> Pin A3|
| RTC SDA -> Pin A4       |        | RTC SDA -> Pin A4       |
| RTC SCL -> Pin A5       |        | RTC SCL -> Pin A5       |
| LED -> Appropriate Pin  |        | LED -> Appropriate Pin  |
| Buzzer -> Appropriate Pin|       | Buzzer -> Appropriate Pin|
+-------------------------+        +-------------------------+
```


## CODE 

```
int main() {
    int choice, ticket_number;

    while (1) {
        show_menu();
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                issue_ticket();
                break;
            case 2:
                printf("Enter ticket number to pay: ");
                scanf("%d", &ticket_number);
                pay_ticket(ticket_number);
                break;
            case 3:
                exit(0);
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}
```


# OUTPUT 


* **This is the final working model of the _TICKET TERMINAL DESIGNER_ using VSDSQUADRON-MINI**

* STEPS:

* 1.Connections are made using Breadboard
* 2.LCD display connected to show the number of tickets
* 3.VSDS kit is connected to the software and code dumped
* 4.Here, I have taken BUZZER as the output which indicates the number of buzzers equal to number of tickets
* 5.So the long buzzer helps in open the gates and let the vehicles to move



## SETUP IMAGE


![TICKET terminal image](https://github.com/user-attachments/assets/dee59fd7-e42d-43e2-a257-2af24d9f4068)


## VIDEO OUTPUT


https://drive.google.com/file/d/1whsRJPKMK7vmlpzlHpkQq4Oy5yVEGdv0/view?usp=sharing 


THANKYOU...
XXXXXXXXXX









  








