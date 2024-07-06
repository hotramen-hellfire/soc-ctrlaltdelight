 # Week2: FurElise(♬);

This week we'll look at how the (CLI) commands are implemented in MikeOS. We'll also write a simple command for our operating system which will use existing system calls.

> [BIBLE](https://mikeos.sourceforge.net/handbook-appdev-asm.html) (nasm)  
> This is quite an important text for you.

## TELLJOKE
###  ♙  Level 1 [+5xp]
We'll implement a basic command `TELLJOKE` that prints a joke to the terminal.

 - You only need to modify the `cli.asm` file. Try tracing other similar commands like `HELP`, `TIME` to get some intuition.
 - You will not have to call any other function than `os_print_string`.
 - While exploring the `TIME` command, try to find out:
 - How is the time string fetched?? Do you find anything peculiar about some functions like `os_print_string` and `os_get_time_string` with respect to the other functions in the code not prefixed by `os_*` ?
 - Where are these functions declared?
###  ♖ Level 2 [+5xp]
We'll extend the functionality of the `TELLJOKE` command, this time it is expected to print a joke randomly from a predefined set of jokes.

 - You only need to modify the `cli.asm` file. Try tracing other similar commands like `HELP`, `TIME` to get some intuition.
 - You will have to use function other than `os_print_string`, try to find out is there a special function that might help you introduce stochasticity?
 - As you are new to writing in assembly, you might want to lookup
    - How to declare strings in *nasm*?
    - How to declare an array in *nasm* with elements of specific sizes?
###  ♚ Level 3 (BOSS) [+10xp]
> WARNING !!: Please do not use headphones while coding this up!! The sound produced might be quite shrill if you mess up. Use your PC's speakers with low volume.  

This is the boss for today, now after writing the joke you'll have to ~~play~~ ***code*** some music. However, the problem statement is quite simple you'll have to tinker around a bit.
 - Use your BIBLE to find out how does music work in MikeOS. I hope that you have fixed you `-soundhw invalid option` warning by now, as described in `Welcome()`. 
 - You'll need this: [FREQUENCIES](https://muted.io/note-frequencies/).
 - Keep all your `ax` arguements > 2000, this improves the sound quality.
 - Rather than coding all the notes by yourself, you can:
	 - Figure out the notes for the music you want to play. For Fur Elise you can go with the iconic ED#ED#EBDCA.
	 - Write the code for the some of the starting nodes as to create a repetitive structure where you just have to change the frequency and the time for which this note has to be played and use this to write a function. (Do not forget to preserve registers that you are changing in the function, if any)
	 - For example, you can write a function `playthis` which plays `ax` frequency for `bx` milliseconds.

###  ♬Aftermath

> - [ Don't use headphones ⚠️ ] You can see the final product in action here:  [DEMONSTRATION](https://drive.google.com/file/d/1zWu1wiq_luodqhHBkEF_QNK_QHpoLsRG/view?usp=sharing)
> - Choose a tone on your own or create one, so that the these the assignments are fun to check. :)
> # : )
> Next week we'll explore: ***syscalls*** in MikeOS.

 
