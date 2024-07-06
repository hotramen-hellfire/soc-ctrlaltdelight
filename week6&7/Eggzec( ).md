 # Week3, 4: Eggzec(💿);
This week we'll closely inspect the abstraction provided by the kernel, i.e. how are userspace programs handled in MikeOS. How does the interface look for a user, how can he add and run programs of his own? 
To answer these questions, we'll try dissecting the implementations of ***syscalls*** in MikeOS, and then proceed to write one of our own.

> [BIBLE](https://mikeos.sourceforge.net/handbook-sysdev.html) (sysdev)
> This is quite an important text for you.
## Userspace Programs
By now you must be familiar with how commands are handled in MikeOS. Another set of programs you can run are the ones in the programs folder provided in MikeOS. For example, try `keyboard` or `adventure` as inputs in the cli.

 - Trace how the programs are being run, start tracing the assembly files from `cli.asm`.
 - Write a function, `os_say_hello` in `source/features/string.asm`.
 - Try writing a simple program in *nasm* in the programs folder named *meraprog.asm*, are you able to use:
	 - `os_print_string`in *meraprog.asm*? why?
	 - `os_say_hello`in *meraprog.asm*? why?
(Note: look at other `*.asm` userspace programs if you need help)
 - If you can explain the answers to these two questions, you have successfully understood the applications and needs for `syscalls`. Note that all functions in the OS code can be made user accessible. Similar to the *public*/ *private* constructs in C++ classes.
### ∮ A simple task
 - Try converting the `os_say_hello` function that you wrote into a syscall which can be used by userspace programs. Refer to the BIBLE shared.

For now, we will move onto memory management for processes in MikeOS, as standalone problems on syscalls, do not make a lot of sense by themselves. We'll incorporate them into further exercises.
## MemMan in MikeOS
Try tracing how the programs like `keyboard.asm`, `calc.bas` etc. are loaded into memory and run. Start with the `source/features/cli.asm` file and try to answer: -

 - How is the memory mapped out, where are the kernel and userspace programs stored in the memory?
 - How are userspace variables managed in MikeOS?
 - How does the OS know where to load the program code to start execution in the case of `.bas` and `.bin` files?
 - Can you write a program `meraprog.asm` s.t. the program takes a command line argument which is the name of another binary file and executes it? Is there anything special about the second binary file or where it will have to be loaded into the memory?
 [you need to create a `.md` file answering these 4 questions.]
### ∯ Eggzec [[demo]](https://drive.google.com/file/d/1pyv0uEpTejyr0jXr8MHADuOPTVMl01NQ/view?usp=sharing)
- Create a copy of the file `programs/keyboard.asm` with the name `programs/keebored.asm`.
 - Write a program `eggzec.asm`, which takes in input name of a binary file, here, `keebored.bin` and executes it and prints `execution complete!!`, after the keyboard is closed and returns to prompt.
 - You will have to change `keebored.asm` a bit in order to make it compatible for this functionality.
### ∰ Final Boss [+10]
Generalize the above functionality to a syscall `os_exec_bin`, which takes in name of a binary file, executes it and returns to the initial control flow. You can assume the following for simplicity: -
 - The program which uses the syscall is copied at address `32768` in the memory. 
 - The program which needs to be executed is set to be loaded at an address `ADD` which is sufficiently greater than `32768`. Add is provided while making the syscall.
 - Ensure that the register `ax` must contain the address of the `*.bin` filename, `bx` must contain the address break at which the `*.bin` is set to load.
 > # : )

 
