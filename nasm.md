[__Command__](https://github.com/prafdin/prafdin/blob/main/nasm.md#commands) 


# All registers x86 
![image](https://user-images.githubusercontent.com/73192804/110766094-e1691480-8265-11eb-9556-2f3120af2f63.png)

# All registers x86-64
![image](https://user-images.githubusercontent.com/73192804/110771459-93570f80-826b-11eb-8aa4-e84f664db9f5.png)


## General-purpose registers
![image](https://user-images.githubusercontent.com/73192804/110767253-188bf580-8267-11eb-9d1a-f9a1152d68a3.png)

> AX - Accumulator register
> BX - Base register
> CX - Count register 
> DX - Data register

![image](https://user-images.githubusercontent.com/73192804/110771653-cd281600-826b-11eb-9d8a-198fd531dc16.png)
> Rxx has size 64 bit
> Exx has szie 32 bit
> xx has size 16 bit
> Everyone xx register contains two 8 bit parts.

## Index registers
![image](https://user-images.githubusercontent.com/73192804/110768127-fcd51f00-8267-11eb-9923-bf893be8dff1.png)

> SI - source index
> DI - destination index

Usually they contain address pointers on array, but may be used how general purpose registers.

## Stack registers 
![image](https://user-images.githubusercontent.com/73192804/110769695-8802e480-8269-11eb-8c3f-d3df07675130.png)

>SP - stack pointer (pointer on top stack) 
>BP - base pointer (pointer on current frame)

## Control registers 
![image](https://user-images.githubusercontent.com/73192804/110770518-75d57600-826a-11eb-87d2-1f3c117294e4.png)

> IP - instruction pointer (pointer on next instruction)
> FLAGS - register where stored processor state 

## Segment registers
![image](https://user-images.githubusercontent.com/73192804/110771023-1a57b800-826b-11eb-8a45-1e4b8f866793.png)

# Types data

Type | Type in C | Size in bit
---- | --------- | -----------
byte | char | 1
word | short | 2
dword | int/long | 4
qword | long long | 8

# Commands

## Moving 
` mov dst, src `

### Issue moving
![image](https://user-images.githubusercontent.com/73192804/110774684-247bb580-826f-11eb-8f24-15446c3968b2.png)

## Type casting
### [mov]e [s]ign e[x]tend.
mode data out dst in src and add sign bit in upper part dst.
```
 movsx dst , src 
```
![image](https://user-images.githubusercontent.com/73192804/110781578-234e8680-8277-11eb-8c9c-7a5ebf09b87b.png)

### [mov]e [z]iro e[x]tend
mode data out dst in src and ziro sign in upper part dst.
```
movzx dst ,src 
```
![image](https://user-images.githubusercontent.com/73192804/110782035-aec81780-8277-11eb-8ff5-db61a26d176b.png)

### cast dword to qword 
```
mosxd dst ,src 
```
![image](https://user-images.githubusercontent.com/73192804/110782281-fea6de80-8277-11eb-9bf3-e5294f8f9aff.png)

## Addition and subtraction
```
add dst , src
sub dst , src 
```
For long arithmetic
```
adc dst , src ; dst+=src+CF
sbb dst , src ; dst-=src+CF
```

## Multiplication and division 
```
mul(sign version imul) multiplier ; First multiplier contained in RAX/EAX/AX ; Result contained in pair registers RDX:RAX/EDX:EAX/DX:AX ;
div(sign version idiv) divisor ; The divisible contained  in pair registers RDX:RAX/EDX:EAX/DX:AX. 	Quotient contained in RAX , excess in RDX
```
## Bit manipulation 
```
and AH , AL ; AH&=AL
or eax, ebx ; EAX |= EBX
xor rax , [rbx] ; RAX ^= *RBX
not rax ; rax=~rax
```
## Comparative operations 
```
cmp 10 , 5 ; (== 10 - 5 ) Raise flags SF , ZF, CF, OF 
test 10, 5 ; (comparate bits both operands) Raise flags SF , ZF
```
![image](https://user-images.githubusercontent.com/73192804/110785476-0ff1ea00-827c-11eb-87e1-96f6a07411df.png)

## Jump comands 
```
mark :   move eax , edx 
         ...
         jmp mark 
```
```
mov rax, 0
    mov ecx, 5
cycle_start:
    add rax,10
    loop cycle_start ; while ecx !=0 ->cycle_start 

```

Comands | State 
------- | -----
je(equal), jz(zero) | ZF = 0
jg(greater) | SF = 0 , ZF = OF
jl(less) | SF = 1 , ZF != OF
ja(above) | CF = 0 , ZF = 0
jb(below) | CF = 1


# Flags 
![image](https://user-images.githubusercontent.com/73192804/110782354-167e6280-8278-11eb-81ee-d95ab8151136.png)
CF - carry flag 
PF - parity flag 
ZF - zero flag 
SF - sign flag 
OF - owerflow flag 

# Segments program
## .data
Stores initialized global and static variables 
For initialize variable use db,dw,dd,dq(bit,word,double word, quadro word)
![image](https://user-images.githubusercontent.com/73192804/110787982-12a20e80-827f-11eb-96fe-62b2c746b4fd.png)
## .rodata
Stores constants
![image](https://user-images.githubusercontent.com/73192804/110788029-22b9ee00-827f-11eb-806d-48b663b6a963.png)
For initialize variable use db,dw,dd,dq(bit,word,double word, quadro word)
## .bss 
Stores uninitialized global and static variables
For initialize variable use resb,resw,resd,resq(bit,word,double word, quadro word)
![image](https://user-images.githubusercontent.com/73192804/110788086-39f8db80-827f-11eb-8e2f-36d1127871e3.png)

## .text 
Stores program's code
![image](https://user-images.githubusercontent.com/73192804/110788591-e044e100-827f-11eb-8e6a-88a7142bcb4f.png)


### Static array 
Declaration static array:
```
times size_array slot_type size_slot
```
![image](https://user-images.githubusercontent.com/73192804/110788417-a2e05380-827f-11eb-87db-767713349460.png)



