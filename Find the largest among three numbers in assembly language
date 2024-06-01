.model small
.stack 100h
.data
msg1 dw 'Enter 1st num: $'
msg2 dw 'Enter 2nd num: $'
msg3 dw 'Enter 3rd num: $'  
lar dw 'Largest number is: $' 
n1 db ?
n2 db ?
n3 db ?
.code 
main proc
    mov ax,@data
    mov ds,ax
    
    mov ah,9
    lea dx,msg1
    int 21h
    
    mov ah,1
    int 21h
    sub al,48     ;input n1
    mov n1,al

    call newline
    
    mov ah,9
    lea dx,msg2
    int 21h
    
    mov ah,1
    int 21h            ;input n2
    sub al,48
    mov n2,al
    
    call newline   
    mov ah,9
    lea dx,msg3
    int 21h
    
    mov ah,1           ;input n3
    int 21h
    sub al,48
    mov n3,al
    
    l1:
    cmp n1,al       ;n1,n3
    jg l21
    jl l22
        l21: 
        mov bl,n2    
        cmp n1,bl        ;n1,n2
        jg lar_n1
        jl lar_n2
        l22:
        mov bl,n2
        cmp n3,bl        ;n2,n3
        jg lar_n3
        jl lar_n2

    
    lar_n1:
     
    call newline 
    mov ah,9
    lea dx,lar
    int 21h 
    mov ah,2
    mov dl,n1
    add dl,48
    int 21h
    jmp exit
    
    lar_n2:
        
    call newline 
    mov ah,9
    lea dx,lar
    int 21h 
    mov ah,2
    mov dl,n2
        add dl,48
    int 21h
    jmp exit
    
    lar_n3: 
        
    call newline 
    mov ah,9
    lea dx,lar
    int 21h 
    mov ah,2
    mov dl,n3
        add dl,48
    int 21h
    jmp exit
              
newline:
    mov ah,2
    mov dl,10
    int 21h
    mov dl,13
    int 21h  
    ret 
exit:
    mov ah,4ch
    int 21h
    main endp
end main



