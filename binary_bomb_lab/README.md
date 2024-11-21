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
    <img src="main_funct.png"/>
</p>

