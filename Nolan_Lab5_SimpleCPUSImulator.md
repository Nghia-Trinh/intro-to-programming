1.Write the assembly language instructions to add the contents of memory location 7 to the contents of register 2 and store the results in register 0. (This requires three instructions.)

LOAD R1 7
ADD R0 R1 R2
STORE R0 7
        
2.What would be the assembly instructions to do the following computation? (Assume that x and y are in memory locations 6 and 7, respectively.)
            y = x + y;

LOAD R1 6
LOAD R2 7
ADD R0 R1 R2
STORE R0 7
HALT
        
3.Determine what the following assembly language program fragment does. What would the same program fragment look like in JavaScript or Python? (You may refer to the contents of memory locations 5 and 6 as x and y. It's possible to capture this in a single line of JavaScript or Python.)
            LOAD R2 5
            ADD R2 R2 R2
            LOAD R1 6
            ADD R3 R1 R2
            STORE R3 5
            HALT

            x= x*2 + y;
        
4.What would be the assembly instructions to do the following computation? (This notation is neither a high-level language nor assembly language, but sort of a compromise between them.)
            R0 = Mem[7] + R2 - R3

LOAD R1 7
ADD R1 R1 R2
SUB R0 R1 R3
        
5.(optional) Write the instructions for exercise 1 in machine language.

100011011011
100000000110
101011001011



        