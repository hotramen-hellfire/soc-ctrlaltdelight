## SOME `SIDEQUESTS` ON MIKEOS 
(_thanks to Angad_)
1) When an emulator allocates virtual RAM memory to store the kernel code of an operating system like MikeOS, does it create this memory space within the emulator itself or does it use a portion of my laptop’s physical RAM? what about other hardware resources like the HDD and the CPU? 🤔  (+10XP)
2) In the `os_call_vector`, instructions are ordered with respect to the starting point of that section. How do we determine the offset for each instruction? For example, how is the 3*16-byte space determined for instructions like `jmp os_main (0000h)` and `jmp os_print (0003h)`? 🤔 (+10XP)
3) When using a `jmp` instruction, does it direct execution to the location where the command or function is written in the kernel code (features folder), or does it lead to the actual memory location allocated by the emulator for that function? 🤔 (+5XP)
4) Is the `int 10h` instruction considered a system call, and if so, why isn’t it listed under the call vector? 🤔 (+5XP)
> use the MikeOS handbooks!!
