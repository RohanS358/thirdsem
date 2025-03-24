

```
.MODEL SMALL

.STACK 100H

.DATA

    MESSAGE DB 'Hello World$'

    ROW DB 10

    COL DB 40

.CODE

MAIN PROC

    MOV AX, @DATA

    MOV DS, AX

    MOV AH, 00H    ; Set video mode

    MOV AL, 03H    ; Text mode 80x25

    INT 10H

    MOV SI, OFFSET MESSAGE

L1: MOV AH, 02H    ; Set cursor position

    MOV BH, 00H    ; Page number (missing in your code)

    MOV DH, ROW

    MOV DL, COL

    INT 10H

    MOV AL, [SI]

    CMP AL, '$'

    JE L2

    MOV AH, 09H    ; Display character with attribute (not 02H)

    MOV BH, 00H    ; Page number (missing in your code)

    MOV BL, 24H    ; Color attribute: Green background (20H) + Red foreground (04H)

    MOV CX, 01     ; Number of times to display character

    INT 10H

    INC SI

    INC COL

    JMP L1

L2:

    MOV AH, 4CH    ; Exit to DOS

    INT 21H

MAIN ENDP

END MAIN

```
### 2nd program

```
.model small

.stack 100h

.data

   message db 'Hello World$'

   len db 0

   row db 0

   col db 40

   word db 10 dup('$')

   newline db 0dh, 0ah, '$'

.code

main proc

   mov ax, @data

   mov ds, ax

   mov si, offset message

   ll: mov al,[si]

   cmp al, '$'

   je end

   inc len

   inc si

   jmp ll

   end:

   ;video mode set

   mov ah, 00h

   mov al, 03h

   int 10h

   mov si, offset message

   mov di, offset word+2

   l: mov di, offset word+2

   l1: mov al, [si]

   cmp al, '$'

   je nextword

   cmp al,' '

   je nextword

   mov bl, [si]

   mov [di], bl

   inc si

   inc di

   jmp l1

   nextword:

   mov byte ptr [di], '$'

   mov di, offset word+2

    loo:

   mov ah, 02h

   mov bh, 00h

   mov dh, row

   mov dl, col

   int 10h

   l2: mov al, [di]

   cmp al, '$'

   je arko

   mov ah, 09h

   mov bh, 00h

   mov bl, 13h

   mov cx, 01

   int 10h

   inc di

   inc col

   jmp loo

   arko: 

   mov col, 40

   inc row

   cmp byte ptr [si], ' '

   jne check_end

   inc si

   check_end:

   cmp byte ptr [si], '$'

   je finished

   jmp l

   finished:

   mov ah, 4ch

   int 21h

main endp

end main
```

