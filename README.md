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


## Conclution

 By following these steps, you will have a virtual environment set up with the RISC-V toolchain ready for development. This setup allows you to compile and test RISC-V programs.


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

*
   `void issue_ticket()`

 * This function increments the
   `current_ticket`
   counter and prints a message indicating that a new ticket has been issued along with the ticket number.
  
* **Behavior:** Each time this function is called, it simulates issuing a new parking ticket by incrementing 
     the ticket count.
  
*
   ```
  void issue_ticket() {
    current_ticket++;
    printf("Ticket issued: %d\n", current_ticket);
  }
 ```

*
  `void show_menu()`
  

* This function prints the main menu options to the console.
  
* **Behavior:** Provides a user-friendly interface for interacting with the program.
  
*
```
void show_menu() {
    printf("1. Issue Ticket\n");
    printf("2. Pay Ticket\n");
    printf("3. Exit\n");
}
```

**3.Main Function:**

* The main function runs an infinite loop to keep the program active until the user decides to exit.
  
* Inside the loop, it displays the menu using
   `show_menu()`
  , reads the user's choice, and executes the corresponding action using a switch-case structure.
  
* *CASE 1:* Calls
  `issue_ticket()`
   to issue a new ticket.
  
* *CASE 2:* Prompts the user to enter a ticket number and calls `pay_ticket()` to process the payment.
  
* *CASE 3:* Exits the program.
  
* *Default Case:* Handles invalid menu choices by printing an error message.
  
*Behavior:* Manages the flow of the program and user interactions.

*
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
 **Summary:**

* The program provides a basic implementation of a parking ticket vending system.

* Users can issue new tickets and pay for existing tickets through a simple menu interface.
  
* The `current_ticket` variable keeps track of the number of issued tickets.
 
*The program continuously runs, allowing users to interact until they choose to exit.

This code serves as a foundational example of how an automated ticket vending system can be implemented in C. It can be further extended with additional features such as ticket validation, payment processing, and database integration for a more robust solution.


![Screenshot from 2024-06-25 16-06-29](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/b60c264e-baf7-46e0-b955-2c7713e5e0d7)


![Screenshot from 2024-06-25 12-39-04](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/d894a1b2-ca5f-4074-996b-87703f7d6cfa)

 ## 2 OUTPUT

 * Compile the program using `gcc tiketterminal.c` and execute the program using `./a.out` command
   

 ![Screenshot from 2024-06-25 16-21-39](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/204cc40b-8da0-4e3d-98ff-0723164110f4)


 ## 3 Converting the C program to RISC-V instruction set 

 * Compile the code using the RISC-V GCC compiler with the following command:
 * 
   ```
   riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c
   ```

![Screenshot from 2024-06-25 16-35-56](https://github.com/NIVETHAC-12/Number-Summation/assets/173597872/ce9bdc2a-61c4-4661-bd88-092bfd94c4c5)

* Now, switch tab to function your main function and calculation using this command :

```
riscv64-unknown-elf-objdump -d ticketterminal.o |less
```

   




  
   













