 # Week1: Welcome( );
> *Written and Directed by Himanshu Gangwal.*   

We will look at some of the very basic functions and implementations of an operating system. We'll look at a very primitive operating system written in *NASM*.

## M[i](https://github.com/mig-hub/mikeOS)k[e](https://github.com/mig-hub/mikeOS)O[S](https://github.com/mig-hub/mikeOS)
This is the best fit for our purpose, as it is quite ***BASIC*** (intends foreshadowing), in terms of features and can be extended easily due to its small kernel size which takes seconds to compile, as compared to most of the other alternatives.
### Installation
*It is better to try it yourself first, you'll have a great time trying to fix things, however this setup is quite ***BASIC***.*
 - Head onto the GitHub page of MikeOS and clone it onto a suitable location on your system. *It is always better to clear the `.git` folder after cloning. (OCD)*
 - You need to install the following dependencies as it is evident from the `build-linux.sh` script, viz. `nasm`, `mkisofs`, `mkdosfs`. Use your package manager to install these, you can use a quick google search for the package names. *Note: `mkisofs` and `mkdosfs` are a part of `cdrkit` and can be installed as `pacman -Sy cdrkit`  if `pacman` is your package manager.* (I am using [Mabox Linux](https://distrowatch.com/table.php?distribution=mabox) in case you were wondering)
 - Now you can run the `./build-linux.sh` which will create the required image.  *Read: `disk_images/README.TXT` for info on the image.*
 - Now we need to install `qemu-system-i386` as required to emulate the OS image. `sudo apt install qemu-system` or `sudo pacman -Sy qemu-full`, will suffice.
 - Now run `./test-linux.sh`, it should give an `-soundhw` error. You can simply remove `-soundhw pcspk` from the command in the script, as believe me listening to ***Kendrick*** is much better.   *Fix-> [see here](https://www.reddit.com/r/qemu_kvm/comments/xte6kq/how_do_i_use_pcspk_now_that_soundhw_is_deprecated/). You can also remove the unidentified file system warning-> [here](https://unix.stackexchange.com/questions/276480/booting-a-raw-disk-image-in-qemu).*

 *`qemu-system-i386 -audiodev pa,id=audio0 -machine pcspk-audiodev=audio0 -drive format=raw,file=disk_images/mikeos.flp` is the final command that I am using.* We're done with the set up :)
## Activity: "My Name Is"
This, being an introduction, is quite simple. All you need to do is add a suitable introduction to your command-line interface in MikeOS.
![before intro](https://github.com/hotramen-hellfire/playground/blob/main/mikeOS/grimgur/w1~intro.png?raw=true)  
add an intro of your choice:  
![added intro](https://github.com/hotramen-hellfire/playground/blob/main/mikeOS/grimgur/w1~intro2.png?raw=true)   
You can solve this without knowing *NASM* completely. Take this as a puzzle.
## NASM
these are some introductory references (in order of resourcefulness):  
[CREATECODE](https://cratecode.com/info/nasm)  
[ASMTUTOR](https://asmtutor.com/)  
You do not need to complete all the exercises here; just try to get an intuition of the way in which *NASM* programs are written. A better way to learn is to read the code and google for what different constructs in the language do. In order to understand the workings of MikeOS, you will have to read a lot of code. The exercises will be quite simple if you know the codebase well.

> # : )
> Next week we'll explore: how to add a new command to the ***CLI***.

 
 
