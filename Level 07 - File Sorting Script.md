# Level 7 - File Sorting Script

## Brief
<img width="827" height="130" alt="image" src="https://github.com/user-attachments/assets/594d0c0d-004f-4976-9941-a5a032cada2b" />

<br><br>

This level got extremely complicated - I looked at online forums and it was still very confusing.

This was my solution:

    #!/bin/bash                                                                                                                                                                                                                    
    dir_path="${1:-.}"                                                                                                                                                                                                             
    Sort_dir=$( find "$dir_path" -type f -name "*.txt" )
    echo "'$Sort_dir'"  

I therefore had a look at the solution below: 

    #!/bin/bash

    DIRECTORY="Arena"

    if [ ! -d "$DIRECTORY" ]; then
        echo "Directory does not exist."
        exit 1
    fi
    
    find "$DIRECTORY" -type f -name "*.txt" -exec ls -lh {} + | sort -k 5,5 -h | awk '{ print $5, $9 }'

but I will try to understand it and break it down as best as I can:

<br>

## 1. Shebang and directory definition

      #!/bin/bash

      DIRECTORY="Arena"
        
The first part is simply the shebang line `#!/bin/bash` to ensure bash shell inteprets the script. The directory is a parameter defined as the `Arena` directory.

  
<br>

## 2. if statement

    if [ ! -d "$DIRECTORY" ]; then
        echo "Directory does not exist."
        exit 1
    fi

the if statement accounts for the scenario if there is no directory defined/directory doesn't exist.

`[ ]` is the test command
`-d` is directory
`!` inverts the logic

in other words `[ ! -d $DIRECTORY ]` tests if the `$DIRECTORY` parameter is NOT a directory.

for debugging the `echo` command simply prints the error message stating the directory doesn't exist and has an exit code of 1.

<br>

## 3. find and ls command

The command is tricky:

    find "$DIRECTORY" -type f -name "*.txt" -exec ls -lh {} + 

a. `find` command

    find "$DIRECTORY" -type f -name "*.txt"
    
* `find -type f` for files only
* `-name "*.txt"` specifies all `.txt` files

> output so far:

    Arena/warrior.txt
    Arena/mage.txt
    Arena/archer.txt

b. `ls` command
     
      -exec ls -lh {} +

* The `-exec` command executes the below command from each result of `find` commmand
* `ls -lh` lists the files in long-list formatting, with human-readable file sizes (kb,mb, etc.)
* `{}` is a placeholder that is replaced with matching files
* `+` runs the ls command once with many files passed as arguments - as opposed to once per file - increasing speed of command execution

> output so far:

    -rw-r--r-- 1 maz239 maz239 0 Jul 31 11:04 Arena/archer.txt
    -rw-r--r-- 1 maz239 maz239 0 Jul 31 11:04 Arena/mage.txt
    -rw-r--r-- 1 maz239 maz239 0 Jul 31 11:04 Arena/warrior.txt    

## 4. sort command

    | sort -k 5,5 -h

The `-k` option sorts the file by key i.e., the column. Since size is the 5th column this is set to `5`.

The `-h` sorts taking into account the human-readable sizes i.e., kb, mb

the output from the find and ls command are piped into the sort command

## 5. awk command

    | awk '{ print $5, $9 }'

The `awk` command prints the 5th and 9th columns, size and file name out of the `ls` command

6. Final commmand

The final command is:

    #!/bin/bash

    DIRECTORY="Arena"

    if [ ! -d "$DIRECTORY" ]; then
        echo "Directory does not exist."
        exit 1
    fi
    
    find "$DIRECTORY" -type f -name "*.txt" -exec ls -lh {} + | sort -k 5,5 -h | awk '{ print $5, $9 }'


## AWESOME!!!

### The level is complete - onto the next!


  
