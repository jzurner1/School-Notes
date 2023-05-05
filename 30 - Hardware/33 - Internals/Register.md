A register is a small amount of high-speed memory contained within a [[CPU|processor]]. They are used to store small amounts of data such as the address of the next instruction to be executed, the current instruction being decoded, and the results of calculations from the ALU.

Most registers contain a program counter, a memory address register, a memory data register, a current instruction register, and an accumulator.

In x86 Assembly, for reference, there are a number of different register types:

# General purpose
A general purpose register is a 64-bit/8 byte container. There are 16 of them that can be used, and each of them can be accessed in smaller sections.

The largest section is, obviously, the whole register. That takes up all 8 bytes. Next is a dword, which takes up the bottom ("lower") 4 bytes. Next is a word for the lower 2 bytes, and lastly the lower byte. The "higher" byte takes up the byte right before the lower byte.

While these registers are general purpose, some instructions can only be completed with certain registers.

| Register | Lower dword | Lower word | Lower byte | Higher byte |
| -------- | ----------- | ---------- | ---------- | ----------- |
| rax      | eax         | ax         | al         | ah          |
| rbx      | ebx         | bx         | bl         | bh          |
| rcx      | ecx         | cx         | cl         | ch          |
| rdx      | edx         | dx         | dl         | dh            |
| rsp      | esp         | sp         | spl        |             |
| rsi      | esi         | si         | sil        |             |
| rdi      | edi         | di         | dil        |             |
| rbp      | ebp         | bp         | bpl        |             |
| r8       | r8d         | r8w        | r8b        |             |
| r9       | r9d         | r9w        | r9b        |             |
| r10      | r10d        | r10w       | r10b       |             |
| r11      | r11d        | r11w       | r11b       |             |
| r12      | r12d        | r12w       | r12b       |             |
| r13      | r13d        | r13w       | r13b       |             |
| r14      | r14d        | r14w       | r14b       |             |
| r15      | r15d        | r15w       | r15b       |             |

![[Pasted image 20220831135210.png]]
