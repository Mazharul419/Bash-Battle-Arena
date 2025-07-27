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



### The level is complete - onto the next!


  
