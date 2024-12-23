# VLSI _ NEW TASK
## A C program was written as follows using the code 
       leafpad akhil.c
##and the program is as follows 

              #include <stdio.h>
        int main() {
            int i, sum = 0, n = 60;
            for (i = 1; i <= n; ++i) {
                sum += i;
            }
            printf("Sum of number from 1 to %d is %d\n", n, sum);
            return 0;
        }
##then save the file as and end ot with a .c , after that open the terminal and enter gcc filename(in my case akhil.c) as in ##this case is to compile the c code

                                        
                    gcc akhil.c
## after it run the command given below to execute the code

                     ./a.out
**which on the interface will look something like :**

![Task 1](https://github.com/user-attachments/assets/74fed929-b62f-433f-be05-138e83b87c85)


##Then we use the command 

                    cat akhil.c
##which means to concatenate to view contents of files and akhil.c is the name of file

![task 1 2](https://github.com/user-attachments/assets/13c666dc-634e-427c-b143-5520dff231a3)


##then,  as we are using RISC - V architechture we use the command 

               riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o akhil.o akhil.c
## to generate code that is compatible with RISC-V systems.

## them to check wether the code was sussecfully created or not we run the code : 

                ls -ltr akhil.o
which will confirm wheter the code is successfully created or not 

![Screenshot 2024-12-22 185015](https://github.com/user-attachments/assets/08b4e1c8-25b8-4062-82ab-4f55dc288f45)

##then we run the code 

        riscv64-unknown-elf-objdump -d akhil.o
## which dissassembles the object file (akhil.o) and displays the assembly code (machine instructions) generated by the compiler for the RISC-V architecture

**which looks something like :**

![Screenshot 2024-12-22 185104](https://github.com/user-attachments/assets/785efd51-4b53-4b1f-8072-204d2d51e1dd)

but if we use a command :

        riscv64-unknown-elf-objdump -d akhil.o | less
        
This command disassembles the akhil.o object file into RISC-V assembly instructions (using objdump -d) and then pipes the output to the less command, allowing you to scroll through the disassembled output interactively.  

as we want to view the main section we type 

         /main 
and we press n
we can see the address and the hexadecimal instructions below the address


![Screenshot 2024-12-22 190026](https://github.com/user-attachments/assets/6846fc6b-cac9-4190-aab5-f69ca1124b9b)


in this case the total no of instructions is (101bc - 10184)+4 as each step is incremented by 4 

**thus it has E no of instructions or 14 instructions**

now we run the same command with a slight change of command i.e 

      riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o akhil.o akhil.c
**The number of instructions of main reduces to B which is 11 instructions**


![Screenshot 2024-12-22 190617](https://github.com/user-attachments/assets/14860f1c-4b5f-48c0-ace7-57257fbd1721)


Using -Ofast applies aggressive optimizations for maximum performance. It can make the code faster but potentially less accurate and harder to debug.

Where as -O1 applies basic optimizations that improve performance without significantly increasing compilation time or affecting standards compliance.


Thats all about this task  😊
