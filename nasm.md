[__Command__](https://github.com/prafdin/prafdin/edit/main/nasm.md#commands) 


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

Moving 
` mov src, dst `




