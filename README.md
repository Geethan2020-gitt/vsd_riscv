The program is based on the RISC-V architecture and uses open-source tools to teach people about VLSI chip design and RISC-V. The instructor for this internship is Kunal Ghosh Sir.

<details>
<summary><b>Task 1:</b> C based and RISC-V based programs for sum of first n numbers</summary>   
<br>

C based
------------------------------------------

Install leafpad editor 

*Use the following command for installing leafpad*
```
sudo apt install leafpad
```
Now we need to write a program in c for sum of 1 to n numbers, and save the file as "sum1ton.c"
![Image](https://github.com/user-attachments/assets/08c695df-9a5e-492d-9fd3-a8b24552dd6d)
Now after we compile this and run using the commands :

```
gcc sum1ton.c
./a.out
```
The output of the c code is :
![Image](https://github.com/user-attachments/assets/8383fcbe-0d85-45f3-8aad-e5d5825409e9)
RISC-V based
------------------------------------------

We can view the sum code using the following command :
```
cat sum1ton.c
```
The terminal output of the above the commad :

![Image](https://github.com/user-attachments/assets/9441bbd1-6e1e-4d7f-9a7e-6e3768e7ac39)

For compiling the above code in RISC-V we use the command :
```
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
![o1_input](https://github.com/user-attachments/assets/c131b9bc-9874-49b2-91de-0706cc822201)

Now the file has been saved "sum1ton.o"
In the new tab we need to give the command ``` riscv64-unknown-elf-objdump -d sum1ton.o | less ```

Now the assembly language code for ```O1``` is :
![Image](https://github.com/user-attachments/assets/96c0a146-d68b-4e02-9208-d8f83ffc93dc)
Here if we calculate the number of instructions, we get the total instructions as 11.
It is calculated as 
``` 
101c0 - 10184 = 3c
3c/4 = f  => 15
```
Now similarly we need to execute the code for ``` Ofast ``` command

The input is shown as :
![Ofast_input](https://github.com/user-attachments/assets/540e85aa-e6cc-47ef-bdf0-20f368c8fa88)

The output of the ``` Ofast ``` command is :
![Image](https://github.com/user-attachments/assets/b4d44d6d-97a7-4551-bed0-1900a4f662ac)
gain if we calculate the number of instructions , we get the instructions as 11.
It is calculated as 
``` 
100e0 - 100b0 = 30
30/4 = c  => 12
