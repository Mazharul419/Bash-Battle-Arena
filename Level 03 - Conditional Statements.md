# Level 3 - Conditional Statements

## Brief
<img width="838" height="138" alt="image" src="https://github.com/user-attachments/assets/97b15dd6-2901-4007-8f82-aeb47ad0988f" />

<br><br>
## Approach
-Use vi to create file
-Use if statement to check if hero.txt is in Arena directory

<br>

## 1. File creation

For this level - a script is created using `vi` command with shebang line

    $ vi level2.sh

in `vi`

    #!/bin/bash    
    file=./Arena/hero.txt
<br>

## 2. if statement logic
The basic if statement will go

    if [ EVENT ]
    then
          echo "Hero found!"
    else
          echo "Hero missing!"

<br>

## 3. File search command

For the command to search for a file existence within the directory the `[]` symbol is used to search with the `-e` argument [returning a true value if a file exists](https://www.cyberciti.biz/tips/find-out-if-file-exists-with-conditional-expressions.html)

It looks like this:

    [ -e $file ]

## 4. Combining commands together

Combining commands from 1-3 gives:

    #!/bin/bash                                                                                                                                                              
    
    file=./Arena/hero.txt                                                                                                                                                       
    
    if [ -e $file ]                                                                      
    then                                                                                          
        echo "Hero found!"                                                            
    else                                                                                          
        echo "Hero missing!"                                                          
    fi

To run this it has to be executable - so saving and exiting out of vi:

    chmod +x ./level2.sh

All that's left is to run the command:

    $ ./level2.sh                        
    Hero missing!

It appears successful - however, so that I am confident it works - I replaced hero with mage.txt (this file defo exists) and it gave me the correct result.

    ./level2.sh                        
    Mage found!

## AWESOME - it works so the result is correct!!!

### The level is complete - onto the next!


  
