> # Level 2 - Variables and Loops
## Brief

<img width="774" height="99" alt="image" src="https://github.com/user-attachments/assets/648a8506-590b-4e7d-8364-b41d0e32e4fe" />
<br><br>

For this level a custom shell script is made to save time printing out individual numbers to the console

<br>

## 1. Creating shell script, Shebang and Variable defining

To do this the file is created in `vi` text editor:

    $ vi level1.sh                    

This opens up the editor - starting all scripts with the shebang line ensures the bash shell interprets this - the variable num is defined:

    #!/bin/bash                                                                                                                                                                 
    
    num=1

<br>

## 2. While loop

A while loop is defined to iterate the count of the numbers until it is equal to 10 using the -le argument:

    while [ count -le 10 ]

Between the `do` and `done` commands: 

The `num` variable is printed using the `echo` command

The value of `num` is increased by one using `++`

    do                                                                     
        echo "$num"                                                                           
        ((num++))                                                                     
    done             

<br>

## 3. Combine and test!

Combining these into one script gives:

    #!/bin/bash                                                                                                                                                                 
    
    num=1

    while [ count -le 10 ] do
        echo "$num"                                                                           
        ((num++))                                                                     
    done  

Using ls to verify the file is there:

    $ ls                                 
    Arena  level1.sh

Also use `chmod +x` to give it executable permissions:

    $chmod +x level1.sh

The command is run to test if it works:
    
    $ ./level1.sh                        
    ./level1.sh: line 8: syntax error near unexpected token `done'                        
    ./level1.sh: line 8: `done'                
    
> ### damn - time to debug
<br>

## 4. Getting humbled... and debugging

Line 8 went wrong so inspecting using vi:

    #!/bin/bash                                                                                                                                                                 
    
    num=1                                                                                                                                                                       
    while [ count -le 10 ] do                                                                                            
        echo "$num"                                                                           
        ((num++))
    done

When it comes to commands in vi - having them on the same line will not work unless they are seperated by a `;` - I will place this before the `do` command so this should work.

    #!/bin/bash                                                                                                                                                                 
    ...                                                                                                                                                                       
    while [ count -le 10 ] do                                                                                            
    ...

Also something I feel stupid about looking at this now... 

> I defined `num` as my variable -
> yet I used `count` for some odd reason...
> without a `$` symbol...

Ok the corrections are made:

    #!/bin/bash                                                                                                                                                                 
    ...                                                                                                                                                                       
    while [ $num -le 10 ] do                                                                                            
    ...

<br>

## 5. Testing fr fr

Testing this out once more:

    $ ./level1.sh                        
    1                                                                                     
    2                                                                                     
    3                                                                                     
    4                                                                                     
    5                                                                                     
    6                                                                                     
    7                                                                                     
    8                                                                                     
    9                                                                                     
    10
  
## AWESOME!!!

### The level is complete - onto the next!


  
