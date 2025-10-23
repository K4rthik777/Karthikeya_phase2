# 1. GDB baby step 1

> Can you figure out what is in the eax register at the end of the main function? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the  eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Disassemble this.

## Solution:

- I opened the debugger0_a file with gdb command then i used info functions command to get to more all the functions within the file.Among the functions shown i found the main function. then i used disassemble command with main as argument. As mentioned in the clue i found the hexadecimal flag with eax and i used print to get the decimal value. 

```bash 
karthik777@Karthikeya:~$ gdb debugger0_a 
```

```bash
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x0000000000001000  _init
0x0000000000001030  __cxa_finalize@plt
0x0000000000001040  _start
0x0000000000001070  deregister_tm_clones
0x00000000000010a0  register_tm_clones
0x00000000000010e0  __do_global_dtors_aux
0x0000000000001120  frame_dummy
0x0000000000001129  main
0x0000000000001140  __libc_csu_init
0x00000000000011b0  __libc_csu_fini
0x00000000000011b8  _fini
```
<img width="704" height="338" alt="image" src="https://github.com/user-attachments/assets/44f24b46-e6af-4677-8906-bbc7c858872c" />


```bash
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
(gdb) print %eax
A syntax error in expression, near `%eax'.
(gdb) print eax
No symbol table is loaded.  Use the "file" command.
(gdb) print 0x86342
$1 = 549698
```
<img width="704" height="338" alt="image" src="https://github.com/user-attachments/assets/53e49e1e-60dd-4e02-af70-577851f3e108" />



## Flag:

```
picoCTF{549698}
```

## Concepts learnt:

- I learnt how gdb debugger works and also how different commands like info functions, disassemble can be used to reverse engineer the file to get the flag.

## Notes:

- i tried the gdb online debugger and tried to debug it using the assembly mode in the language section. but then i found that it can run on linux terminal so i installed the gdb debugger into my wsl terminal.

# 2. ARMssembly 1

> For what argument does this program print `win` with variables 85, 6 and 3? File: chall_1.S Flag format: picoCTF{XXXXXXXX} -> (hex, lowercase, no 0x, and 32 bits. ex. 5614267 would be picoCTF{0055aabb})

## Solution:

- I opened the chall_1.S file to view the assembly code. In the first func function, i observed that there is one unknown value in the program along with given values 85,6,and 3 these values are used to carry out some operations. The left bit shift operation(lsl) is used on the number 85 with 6 as number of places shifted. Then this new number is divided with 3 using the sdiv operation then this result is finally subtracted with the unknown value using sub operation. In the main function, the final result is checked if it is 0 using cmp operation and if it turns out to be 0 then win is printed. So this final value when converted into hexadecimal is the flag.  
 the func function 

<img width="397" height="646" alt="image" src="https://github.com/user-attachments/assets/b657a7dc-0b1d-4af9-bad4-8bb024f396be" />

the main function

<img width="328" height="827" alt="image" src="https://github.com/user-attachments/assets/496972d4-a01a-45ed-9134-5781469881e0" />


## Flag:

```
picoCTF{00000715}
```

## Concepts learnt:

- I learnt how to read ARM assembly code and interpret it to know how the program works.

## Notes:

- I didn't know ARM assembly code before this so i just learnt what each syntax meant and what it did to understand what the program what doing.

## Resources:


- (https://developer.arm.com/documentation/107829/0201/Example--decrement-until-equal/Investigate-NZCV-flags-with-Arm-Development-Studio)


