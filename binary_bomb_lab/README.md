# BINARY-BOMB-LAB: FROM OPEN SECURITY 2
## EXPLAINATION:
You are given an .exe file, try to deduce what the program expects for input so the bomb doesnt explode! <br/>
There are 6 phases, with (probably) increasing difficulty.<br/>

## GUIDE:
- Try to step over each line to understand the assembly instructions.
- Ignore unnecessary blocks of instructions (stack overflow detection, etc.)

## PHASE 1:
- let's set a bp at main 1st. <br/>
<p>
    <img src="main_funct.png"/>
</p>
