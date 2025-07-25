> # Level 1 - The Basics
## Brief

<img width="837" height="131" alt="image" src="https://github.com/user-attachments/assets/a946f7b3-796f-4945-a51c-699a5cf374bf" />
<br><br>

For this level to make the `Arena` directory the `mkdir` command is used:

    maz239@DESKTOP-0MHOS00:~/VSCODE/Bash_Battle_Arena$ mkdir Arena                        

Verify its been created using `ls` command:

    maz239@DESKTOP-0MHOS00:~/VSCODE/Bash_Battle_Arena$ ls
    Arena
<br><br>
Great - using the touch command the files for warrior, mage, and archer can be created.

I usually `cd` into the `Arena` directory but I wanted to find a way without having to do this: 

Which is through `./` which mean `current directory`

One hack I found online to [make multiple files](https://unix.stackexchange.com/questions/338909/without-changing-your-current-directory-create-an-empty-file-in-another-directo) is using curly braces `{}` - which is awesome!

Combining these into one command:

    maz239@DESKTOP-0MHOS00:~/VSCODE/Bash_Battle_Arena$ touch ./Arena/{warrior.txt,archer.txt,mage.txt}
Once more using ls to check `Arena` for the files:
    
    maz239@DESKTOP-0MHOS00:~/VSCODE/Bash_Battle_Arena$ ls ./Arena/
    archer.txt  mage.txt  warrior.txt

## AWESOME!!!

### The level is complete - onto the next!


  
