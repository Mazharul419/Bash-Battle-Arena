# Level 6 - File Parsing

## Brief
<img width="1092" height="185" alt="Screenshot 2025-07-27 12 25 15" src="https://github.com/user-attachments/assets/428d317f-c1ef-4bf4-a3d3-d9be9b870b83" />

<br><br>

For this level my approach is using a parameter to define the file - then using the wc command output the lines the file has.

<br>

## 1. Create .sh file

As usual file is created using `vi` and shebang line inputted:

    $vi level6.sh

in vi:

    #!/bin/bash

<br>

## 2. Create function

For these commands moving forwards - I will using functions for these scripts so I can recall them easily - this avoids having to manually type out scripts moving forwards.

To define the function - I will name the file `file_parser` followed by `()` and then curly braces `{}`:

        file_parser() {
        
        }

The content within `{}` will define what this function does.

<br>

## 3. Define file path

To define the file path which the user will input - the local variable `file_path` is used - which is a user-inputted parameter, denoted by a `$1`:

    local file_path="$1"

## 4. Create line-counting command

The command which is used to read the # of lines of the file is the `wc` command with the `-l` argument. 

Using the `cat` command as standard input using `|` symbol avoids unneccessary repetition of the file name:

    cat "file_path" | wc -l

5. Full function

The final function is:

        #!/bin/bash

        file_parser() {
        local file_path="$1"
        cat "file_path" | wc -l
        }

Exiting vi - it is given executable permissions using `chmod +x` - I then execute using
        
        file_parser() "./file.txt"

where file.txt is a regular text file with test1, test2 etc.. for each line up to 5.

I recieved the following error message:

        -bash: syntax error near unexpected token `"./file.txt"'

## > I got this wrong

## Debugging

I attempted to debug - but do not see what I did wrong - I already spent a lot of time on this so I will compare my solution to the correct one:

        #!/bin/bash

        if [ -z "$1" ]; then
            echo "No file provided"
            exit 1
        fi
        
        if [ ! -f "$1" ]; then
            echo "File not found!"
            exit 1
        fi
        
        LINE_COUNT=$(wc -l < "$1")
        echo "The file '$1' has $LINE_COUNT lines."

A few lessons here:

 1. I did not add `if` statements denoting the possibilities of the file not being provided or it not being a regular file (or existing at all!)
 2. Function was not used - though clarification is needed what a function would look like.
 3. The parameter `$1` has double quotation marks on it when referenced - only exception to this is when it is within a set of double quotation marks in which case it is single to avoid closing it.
 4. The line count command is defined as LINE_COUNT and references using $ in an echo command so this can be printed to the user - so they know the number of lines - this is something I was stuck on.

To test if I truly learnt my lesson - I attempted to recreate the same file using the lessons above:

<img width="1077" height="569" alt="image" src="https://github.com/user-attachments/assets/8f780691-5a74-44f8-82d9-ff56a95d5d21" />

Testing results in:

<img width="1133" height="303" alt="image" src="https://github.com/user-attachments/assets/3861c1bf-3bcb-4feb-b1c6-3419c0855d4a" />

### The script is correct and the level is complete - onto the next!
