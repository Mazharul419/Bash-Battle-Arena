# Level 5 - Boss Battle - Combining Basics

## Brief
<img width="818" height="256" alt="image" src="https://github.com/user-attachments/assets/cf6d6cc9-c251-475f-9a53-486d7c53719e" />
<br><br>

The approach to this level is to:

  1. Create `Battlefield` directory
  2. Create `.txt` files
  3. Check for `knight.txt` and move to `Archive`
  4. List contents of both directories
<br>

## 1. Create Battlefield directory

The script file is first created using vi with the shebang line:

    $vi level 5.sh

script:

    #!/bin/bash

To create the `Battlefield` directory the mkdir command with -p option is used

    mkdir -p Battlefield

<br>

## 2. Create .txt files

Using the touch command with curly braces `{}` the files `knight.txt`, `sorcerer.txt` and `rogue.txt` will be created inside the `Battlefield` file

    touch ./Battlefield/{knight.txt,sorcerer.txt,rogue.txt}

<br>

## 3. Check for knight.txt and move to Archive

For this part the [] operator with -e argument is used to search for `knight.txt` within the `Archive` directory

The file parameter is defined first:

    file=./Battlefield/knight.txt

    if [ -e $file ]
    then
    ...
    fi

to define the remainder of the `if` statement: 

if the knight is found, using the `mv` command this will be moved to 'Archive' - created using `mkdir -p` once more.
if not - the script simply prints "Knight missing!"

    ...
    then
      mkdir -p Archive
      mv $file Archive
    else
      echo "Knight missing!"
    fi

Combining these two gives the full command for this section:

    file=./Battlefield/knight.txt
    touch ./Battlefield/{knight.txt,sorcerer.txt,rogue.txt}
    
    if [ -e $file ]
    then
      mkdir -p Archive
      mv $file Archive
    else
      echo "Knight missing!"
    fi

## 4. List contents of both directories

To list the contents of both directories the `ls` command is used:

    ls Battlefield Archive

5. Final command

Below is the final command combining steps 1-4:

    #!/bin/bash

    mkdir -p Battlefield
    touch ./Battlefield{knight.txt,sorcerer.txt,rogue.txt}    
    file=./Battlefield/knight.txt

    if [ -e $file ]
    then
      mkdir -p Archive
      mv $file Archive
    else
      echo "Knight missing!"
    fi

    ls Battlefield Archive

Using chmod +x this script will be executable:

    $chmod +x level5.sh

Running the command:

    $./level5.sh

<img width="1358" height="293" alt="image" src="https://github.com/user-attachments/assets/7b463b4a-7dcd-4b9f-9fd6-6eacf42b68f4" />
>OUCH! The files aren't in the correct space!!!

Reviewing the script to see what went wrong -
<img width="1191" height="48" alt="image" src="https://github.com/user-attachments/assets/5744b2a0-b25a-4e2d-8ca3-d828abeeb279" />

1. There is no `/` between the `Battlefield` directory and the files, so the path is not specified
2. There is normal braces instead of curly braces

Fixing these give:

<img width="1221" height="51" alt="image" src="https://github.com/user-attachments/assets/f63fa7b8-1059-468d-afde-5335d0da0d8c" />

Exiting vi and re-running the script:

    $./level5.sh
    Archive:
    knight.txt

    Battlefield:
    rogue.txt sorcerer.txt

## AWESOME!!!

### The output is correct - therefore the level is complete - onto the next!
  
