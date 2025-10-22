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
![alt text](image-1.png)

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
![alt text](image-2.png)


## Flag:

```
picoCTF{549698}
```

## Concepts learnt:

- I learnt how gdb debugger works and also how different commands like info functions, disassemble can be used to reverse engineer the file to get the flag.

## Notes:

- i tried the gdb online debugger and tried to debug it using the assembly mode in the language section. but then i found that it can run on linux terminal so i installed the gdb debugger into mmy wsl terminal.
- 

## Resources:

- https://www.geeksforgeeks.org/c/gdb-step-by-step-introduction/