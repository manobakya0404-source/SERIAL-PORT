
# SKILL ASSSESMENT 2.

## AIM
To Write an assembly language program in 8051 to generate a 1 second delay using Timer 1 in Mode 1 and toggle all bits of Port 1 continuously.


## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM
```
ORG 0000H

MAIN:   MOV P1, #0FFH      
        MOV TMOD, #10H      
HERE:   ACALL DELAY        
        MOV A, P1            
        CPL A                
        MOV P1, A            
        SJMP HERE            

DELAY:  MOV R2, #20         
AGAIN:  ACALL DELAY50        
        DJNZ R2, AGAIN      
        RET

DELAY50: MOV TH1, #3CH       
         MOV TL1, #0B0H      
         SETB TR1            
WAIT50:  JNB TF1, WAIT50    
         CLR TR1             
         CLR TF1             
         RET

END
```

### OUTPUT:
<img width="1919" height="1199" alt="Screenshot 2025-10-30 144147" src="https://github.com/user-attachments/assets/4544bfb6-1b94-4c02-a8fe-9a8c24676ea1" />

<img width="1919" height="1199" alt="Screenshot 2025-10-30 144204" src="https://github.com/user-attachments/assets/bc469896-4fed-4556-9379-a0c5bf638eea" />

### RESULT:
Thus the assembly language program in 8051 to generate a 1 second delay using Timer 1 in Mode 1 and toggle all bits of Port 1 continuously by using 8051 KEIL was done and shown the output.
