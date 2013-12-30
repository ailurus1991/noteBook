# Shebang (Unix)
Shebang is the character sequence consisting of the characters number sign and exclamation mark, that is *#!*. For basic bash in Linux, change it from

    #!/usr/bin/bash

to

    #!/usr/bin/env bash

For example, in Python or Ruby, we can change it from 

    #!/usr/bin/python

to 

    #!/usr/bin/env python

Therefore, we can use the right python in different computers/environment variables.

# positional parameters
Since *$* stands for the *input parameters*, and *#* stands for the *number*. So we have:

    #!/usr/bin/env bash
    echo "
    Number of arguments: $# # this stands for the number of parameters (not includes the file name)
    The program name is: $0 # this should be the 0th parameter (the filename actually)
    The first argument is: $1 # this should be the 1st parameter (just the parameter after the script's name)
    "
# if
Here the condition in *if* is actually a command, if the command is executed well and return validly (valid: 0, invalid: non-zero).

    if [ $# != 1 ]
    then
        echo "hehe"
        exit 1
    fi

### Tips

* notice the space 
* check the return value of a command: 1. _ls_; 2. _echo $?_
* use *exit 1* to exit the whole bash program

# re-direct (>)
For stand input/output/error, if we user *>* in our command, the error messages will be redirected in to another file, such as:

    echo """
        ERROR: missing operand
        Usage: ./xxx.sh PATHNAME
         """ >&2

Here *>&2* is the error message redirection, which means that *even we do ./xxx.sh >error.txt*, the error message will still be printed on the screen.

# for loop
Here's just an example:

    #!/usr/bin/env bash
    for i in 1 2 a b
    do
        echo $i
    done

Use *``* to execute the command at first and give the return results to the for loop:

    #!/usr/bin/env bash
    for i in `ls`
    do
        echo $i
    done

# echo -n and setting default value
Sometimes we need to ask for answer:

    echo -n "Want to delete: $file? (Y/n): " // get the user's keyboard input
    read AAA // read the keyboard input to variable AAA
    if [ "${AAA:-y}" = "y" ];then // if no input we just set the AAA = y as the default value
        echo delete $file
        rm $file
        echo ...done
    else
        echo pass
    fi

Hence the whole script is asking user delete the files in current directory or not:

    #!/usr/bin/env bash

    if [ $# != 1 ]
    then
        echo """
    ERROR: missing operand
    Usage: ./delete_or_not.sh PATHNAME
             """ >&2
        exit 1
    fi

    cd $1
    for file in `ls`
    do
        echo -n "Want to delete: $file? (Y/n): "
        read AAA
        if [ "${AAA:-y}" = "y" ];then
            echo delete $file
            rm $file
            echo ...done
        else
            echo pass
        fi
    done
