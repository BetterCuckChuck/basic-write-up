# BINARY-BOMB-LAB: FROM OPEN SECURITY 2
## EXPLAINATION:
You are given an .exe file, try to deduce what the program expects for input so the bomb doesnt explode! <br/>
There are 6 phases, with (probably) increasing difficulty.<br/>

## GUIDE:
Try to step over each line to understand the assembly instructions.
Ignore unnecessary blocks of instructions (stack overflow detection, etc.)

## PHASE 1:
- let's set a bp at main 1st and check out the asm code. <br/>
<p>
    <img src="main_funct.png"/>
</p>

noteworthy instructions:
+ 2 printf and readline line (presumably for displaying some texts and reading required input from users. <br/>
+ the phase_x and phase_defused funct go hand in hand. <br/>
-> theory: phase_x funct will check for bomb in the x phase, if bomb -> explode, if not, move onto phase_defused and continue the next phase. <br/>

let's check out the phase_1 funct next. <br/>
<p>
    <img src="phase1_funct.png"/>
</p>

we can see a call to (string_not_equal) (probably 4 comparing string), as well a lea (with symbol bomb!'string') and a mov above. <br/>
-> theory: these are ptrs to the required string and our input string, respectively. <br/>
we can use da (access memory and displaying them as ascii) -> giving us "I am just a renegade hockey mom." for rdx and our input for rcx. <br/>
-> our answer for phase_1: I am just a renegade hockey mom.

## PHASE 2:
let's check out phase_2 funct:
<p>
    <img src="phase1_funct.png"/>
</p>
