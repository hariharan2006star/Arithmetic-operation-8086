## HARIHARAN N(212223060079)
# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     1200 : 12           |      1204 : 24           |
1201 : 34  |  1205 : 68
1202 : 12   | 1206 : 00
1203 : 34    |1207 : C4

  
#### Manual Calculations

![ADD](https://github.com/user-attachments/assets/ba563f0d-3152-43ff-86be-2f6dba6b2781)

---

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="633" height="418" alt="Screenshot 2025-09-07 152242" src="https://github.com/user-attachments/assets/01b4bb3b-d9ea-4f4d-96b0-cdc221b80039" />

<img width="636" height="427" alt="Screenshot 2025-09-07 152151" src="https://github.com/user-attachments/assets/d125bd51-3c8a-4874-b150-39d6c3231029" />

## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />

#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|               1200 : 12          |      1204 : 00                    |
1201 : 34 | 1205 : 00
1202 : 12 | 1206 : 00
1203 : 34 | 1207 : C4

#### Manual Calculations

![SUB](https://github.com/user-attachments/assets/9b1b50d0-0940-4400-9597-254099ff3cb0)


---


## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="633" height="425" alt="Screenshot 2025-09-07 150154" src="https://github.com/user-attachments/assets/82c99bf0-d251-4d71-9af1-5cb2539aa508" />

<img width="641" height="429" alt="Screenshot 2025-09-07 144637" src="https://github.com/user-attachments/assets/4d640051-af78-4b15-8674-caa80e2d31c2" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

## FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />




#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|         1200 : 12                |       1204 : 44                   |
1201 : 34 | 1205 : 51
1202 : 12 | 1206 : 97
1203 : 34 | 1207 : 0A

#### Manual Calculations

![MUL](https://github.com/user-attachments/assets/c411faa5-07fa-4791-8adc-cec6a5a2df32)


---

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="631" height="412" alt="Screenshot 2025-09-07 145147" src="https://github.com/user-attachments/assets/788248d8-0925-482b-8d8a-0f94bfaba85f" />
<img width="521" height="355" alt="Screenshot 2025-09-07 152950" src="https://github.com/user-attachments/assets/487283a6-dd99-4f50-ab13-35aa98768b61" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200 : 12                  |              1204 : 01            |
1201 : 34 | 1205 : 00
1202 : 12 | 1206 : 00
1203 : 34 | 1207 : 00

#### Manual Calculations

![DIV](https://github.com/user-attachments/assets/08a18b5e-f9e7-4d3b-979f-b2c6585358a3)


---
## OUTPUT FROM MASM SOFTWARE
<img width="631" height="425" alt="Screenshot 2025-09-07 151350" src="https://github.com/user-attachments/assets/d0edcc1c-c9a5-408f-b982-7871bbc3e449" />

<img width="635" height="420" alt="Screenshot 2025-09-07 151310" src="https://github.com/user-attachments/assets/7d8547dd-c87c-44ae-b8b4-dc17b9bd8291" />


## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.
