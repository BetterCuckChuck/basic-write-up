# OPENSECURITY TRAINING 2: WRITE THE FUN INSTRUCTION.
## Challenge description:
Write the raw bytes to create the following assembly sequences:
```asm
mov eax, 0xAABBCCDD
sahf
jz mylabel
and eax, 0x31337
mylabel:
ret
```

## mov eax, 0xAABBCCDD
the opcode for moving imm32 into a r32 register is: B8+ rd id. <br/>
rd - eax: 000. </br>
id - 0xAABBCCDD.

-> Instruction:
```asm
db 0B8h
dd 0AABBCCDDh
```

##sahf
def: store ah into flags <br/>
opcode: 9E  <br/>
-> Instruction:
```asm
db 09Eh
```

## jz label
-> have to calculate offset: 5 bytes
opcode: 0F 84 cd

-> Instruction:
```asm
db 0Fh 84h 05h
```

##and eax, 0x31337
opcode: 25 id <br/>
-> Instruction:
```asm
db 025h
dd 031337h
mylabel:
```

##ret
opcode: C3 <br/>
-> Instruction:
```asm
db 0C3h
```

## FULL INSTRUCTION:
```asm
db 0B8h
dd 0AABBCCDDh
db 09Eh
db 0Fh 84h 05h
db 025h
dd 031337h
mylabel:
db 0C3h
```
