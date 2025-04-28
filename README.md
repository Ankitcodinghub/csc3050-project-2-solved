# csc3050-project-2-solved
**TO GET THIS SOLUTION VISIT:** [CSC3050 Project 2 Solved](https://www.ankitcodinghub.com/product/csc3050-program-2-instruction-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;117524&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSC3050 Project 2 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
Overview

In program 1, you have written an assembler for MIPS Assembly Language, which you take an MIPS code input and convert it to its corresponding machine language (binary) code. Program 2 is called a MIPS Simulator, in which you will take a MIPS code input and simulate executing the code. For example, if an adder MIPS code is given to you, your first program should translate it into a binary code file, and your second program should prompt the user to enter two integers and output the correct answer.

Logic

Unlike the first program in which you are allowed to achieve the goal however you wanted to, you will have some restrictions this time. That is, you will execute the MIPS code just like how a machine does it. The logic behind this program is fairly easy if you understand how machine works. Recall the basic machine cycle, where you load an instruction, increment PC, and execute the loaded instruction. You will do the exact same thing.

With that being said, you will need to:

1. Simulate memory. In your C/C++ program, allocate a block of memory of 6MB, which should be sufficient. This is used to simulate the main memory. For more details of simulating main memory in case you forgot, refer to page A20-A22 of the book (Appendix A). In our case, reserve 1MB for text section. You are going to map the memory address of the block you allocated to 0x00400000, which is a 32 bit address. When you do operations that involve memory, you simply reversely map the 32 bit address back to 64 bit, for access in your computer’s memory. For example, you called malloc for allocating a 6MB of memory, it returned 0x100000000022000, which is a 64 bit address. Then, you give it a name of 0x00400000, which is a 32 bit address. After you do this, everything else will just act normal. In your MIPS when you want to access some memory address, you will simply

calculate the offset of that address from 0x00400000, and add that offset to 0x100000000022000. In short, you will give the 64 bit address a 32 bit “name”.

2. Allocate and maintain memory spaces to simulate the regular 32 registers. Correctly use them, including $fp, $sp, etc. Since we are using a mapping from 64 bit address to 32 bit address, the address can be put in a 32 bit register. You can allocate 4 bytes for each register.

3. Maintain a PC, which indicates the next instruction to load.

4. Maintain a code section in your simulated memory, where the assembled MIPS machine code is put.

5. Maintain a data section in your simulated memory, where the pre-defined data in MIPS code (.data section) is put. Located on top of text section. For dynamic data, it grows towards higher memory address. For the data you read in from .data section, you will line them up in order in data segment of your simulated memory. The first piece of data in .data section of MIPS code will be put at the lowest memory address of your data segment. The rule to put data is each piece of data is going to occupy the full block (4 bytes) even if it used only part

of a block. For example, a string of length 11 is using 11 bytes in memory, and put at address 0x0. Then it used up two full blocks (8 bytes), and 3/4 of the third block, which starts at 0x8. The next piece of data should not be put at address 0xB, instead, it should be put at address 0xC.

6. Maintain a stack section in your simulated memory, which grows towards lower memory address.

7. Simulate what each instruction does using C/C++. This could be done by writing a function for each instruction.

8. Simulate the execution. You are expected to follow the machine cycle. Judge which instruction it is, call the function.

9. You need to support syscall instruction (in your assembler and simulator), which is down below. You also need to support SPIM syscalls below.

Grading

Instruction/syscall execution – 40% each wrongly implemented instruction/syscall will result in 2% deduction.

Memory and register simulation – 30%

Machine cycle – 10%

Coding style/comments – 10%

Report – 10%
