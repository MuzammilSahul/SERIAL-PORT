
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'D' 
WAIT:JNB TI, WAIT
CLR TI 
END



```
### (ii) Serial Port to Transfer a Message

```
ORG 00H
MOV TMOD,#20H
MOV TH1,#0FCH
MOV SCON,#40H
SETB TR1
MOV B,30H
MOV DPTR,#4500H
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
DJNZ  B,AGAIN
END


```

### OUTPUT:
<img width="843" height="920" alt="image" src="https://github.com/user-attachments/assets/4c02c17d-fa68-4b29-bad1-db571e51ec0d" />
<img width="826" height="1140" alt="Screenshot 2025-10-15 130056" src="https://github.com/user-attachments/assets/78a1154e-d500-4c84-96a2-df90ac172ec1" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
