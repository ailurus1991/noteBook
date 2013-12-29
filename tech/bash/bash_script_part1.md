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
