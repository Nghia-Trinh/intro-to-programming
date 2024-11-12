1. Assemble the assembly language program that is provided when you load the CPU Simulator page by clicking on the "==>" button between the program and the main memory columns. What changed in the simulator as a result? If you're not sure, reload the page and assemble the program again. Why did the assembler translate the number of lines that it did -- why not more or less?
        Answers:
The simulator would appear up a code number in the Main memory box #1 with the code number 100000000110 and the Main memory box #2 111111111111. The assembler will execute the order written inside the Assembly Lang boxes, and automatically provide the numbers inside the main memory boxes for usage.

2. Enter address 0 (or 00) into the Instruction Address or Program Counter (PC) field. Click on the "Fetch" button. What happened in the simulator?
        Answers:
The simulator would take back the counter back to the top after we press the fetch button.

3. What do you think will happen when you click on the "Execute" button? Write your answer before executing. Also write down the values in any registers or memory addresses that you think might change as a result of executing this instruction. Now execute the instruction by clicking on the "Execute" button. What happened? Write down your actual results and see if they match your expected results.
        Answers:
Expected Results		
It will add up the values inside the R0 and R1.	 1000 + 0011 = 1011. The values in R0 may change.
Actual Results:
It adds up R0 and R1.000000001000+ 000000000011 => 000000001011
4. Continue to Fetch and Execute until the simulator halts. How many cycles are required?

        Answers:
The number of cycles required is 1, since right after the add line the counter comes to the hlt line which halts the whole CPU.

5. How many Fetch/Execute cycles do you think would be needed to add the contents of R0, R1, and R2 and store the result in R3? Document your expected results. Modify the assembly language and test your hypothesis. (Don't forget the HALT instruction.) Document the program you used and the actual number of cycles required, including the cycles needed to halt the program.
        Answers:
Expected Results		Actual Results
3 	 	                2
 	 	 
Assembly Language Program:

ADD R1 R1 R2
ADD R3 R1 R0
HALT

6. Using your program from question 5, experiment with different start instructions. (Assuming you executed the HALT instruction when testing your program, you will have to reload the page and re-type in your program.)
a.What happens if you start at address 1?
b.What happens if you start at address 5?
c.What happens if you start at address 9?
d.What happens if you start at address 14?

        ANSWERS:
a.It will add R0 and R1 and place it into R3, but will not execute the addition of R1 and R2.
b.Nothing will happen, since the box is empty.
c.The CPU will go into add funtion, as there has been a string inside that address.
d.Nothing will happen, since the box is empty.

7. What happens if you change the Instruction Address (PC) mid-program? For example, what happens if you change the PC to 01 just before fetching the HALT instruction? (In other words, if your HALT instruction is in memory location 02, change the PC from 02 to 01 before fetching instruction 02.)
        Answers:

It would go back to the address 01.(the address which we had just input in).

8. What happens if you Fetch multiple times before you click the Execute button?

        Answers:
The simulator will keep on moving to the next memory locations.

9. What instruction would store R0 to memory location 14?

        Answers:
The instruction: STORE R0 14.

10. How many Fetch/Execute cycles do you think would be needed to add the contents of memory addresses 07 and 08 and put the results in memory address 15? Document your expected results. Write an assembly language to do this and test your hypothesis. (Don't forget the HALT instruction.) Document the program you used and the actual number of cycles required, including the cycles needed to halt the program.

        Answers:
Expected Results		Actual Results
5 	 	                5
 	 	 
 	 	 
Assembly Language Program:
LOAD R1 7
LOAD R2 8
ADD R0 R1 R2
STORE R0 15 
HALT

11. Write a program that takes a value in memory location 07 and doubles it, storing the result in memory location 08. Test your program, then insert it in your lab write-up document.

        Answers:
LOAD R0 7
ADD R0 R0 R0
STORE R0 8

12. What sequence of assembly-language instructions corresponds to the following machine-language program?
 
        100000000000 
        101011000011 
        111111111111

        Answers:
ADD R0 R0 R0
STORE R0 3
HALT

13. In English, what overall task does the previous machine-language program perform?

        Answers:
It would multiply the values inside of the register R0 by 2, and then store the value inside the register R0. After that, the simulator would go on and store the value from register R0 to the memory location 3. The program will go to halt at the end.

14. What do you think would happen if you forgot to place a HALT instruction at the end of a machine-language program? How would the control unit react? Use the simulator to test your prediction, then report the results.

        Answers:
The program will continue to take on the instructions below as we press on the Fetch button. 

15. Write a sequence of assembly-language instructions to cause the contents of the four registers to be copied into memory locations 7, 8, 9, and 10, respectively.

        Answers:
STORE R0 7
STORE R1 8
STORE R2 9
STORE R3 10

16. Write the sequence of machine-language instructions that corresponds to the assembly-language program you wrote for the previous question.

        Answers:
101011 00 0111
101011 01 1000
101011 10 1001
101011 11 1010

17. Write a sequence of assembly-language instructions to add the contents of memory locations 10, 11, and 12 and then store the result in memory location 13.

        Answers:
LOAD R1 10
LOAD R2 11
LOAD R3 12
ADD R0 R1 R2
ADD R1 R0 R3
STORE R1 13

18. Write the sequence of machine-language instructions that corresponds to the assembly-language program you wrote for the previous question.

        Answers:
100011011010
100011101011
100011111100
100000000110
100000010011
101011011101

19. Write a sequence of assembly-language instructions that multiplies the contents of memory location 07 by four. For example if the number 10 were stored in memory location 07, executing your instructions would cause the simulator to store 40 there. Note: Although the CPU Simulator instruction set does not include a multiplication operation, a number can be multiplied via repeated additions.

LOAD R1 7
ADD R1 R1 R1
ADD R1 R1 R1
ADD R1 R1 R1
ADD R1 R1 R1

