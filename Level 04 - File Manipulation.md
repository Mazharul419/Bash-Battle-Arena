# Level 4 - File Manipulation

## Brief
<img width="764" height="130" alt="image" src="https://github.com/user-attachments/assets/c5b7b8c9-c69a-4666-ac94-66519b217570" />

<br><br>
> For this attempt I researched online how to utilise the `cp` command to copy a folder and its contents.
> I couldn't find an appopriate solution and was stuck for an hour - I therefore looked at the solution.
> This is posted step-by-step, with explanation
<br>

## 1. Creating file
Using the `vi` command the file is created

    $vi level4.sh

Once in the file the `shebang` line is created

    !#/bin/bash

<br>

## 2. mkdir

Using the `mkdir` command with `-p` option the new Backup file is created:

    mkdir -p Backup

<br>

## 3. mv

Using the `mv` command the contents of `Arena` is moved to `Backup`

To specify contents with `.txt` extension in `Arena` the `/*.txt` is used where

  `*` means all files
  `.txt` is files that are text files

the command is:

    mv Arena/*.txt Backup

<br>

## 4. Combining commands together

Combining all the commands together as follows:

    #!/bin/bash

    mkdir -p Backup
    mv Arena/*.txt Backup

Once saved and exited - in the command line the exectuable permission is given using the `chmod` command

    $chmod +x level4.sh

It is then executed:

    $./level4.sh

To check if the `Backup` folder is created with its content I will use `ls`

    $ls
    Arena  Backup  level1.sh  level2.sh  level3.sh  level4.sh

The folder is there - `ls` the `Backup` to check contents:
    
    $ls Backup
    archer.txt  mage.txt  warrior.txt

## AWESOME!!!

### The contents match Arena, so the level is complete - onto the next!


  
