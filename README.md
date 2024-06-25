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


### Conclution

 By following these steps, you will have a virtual environment set up with the RISC-V toolchain ready for development. This setup allows you to compile and test RISC-V programs.




#### Task 2
   **PROJECT 1 - Ticket Terminal Designer: Developing an Automated Parking Ticket Vending Machine**
   













