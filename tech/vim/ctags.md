# Before 
The basic usage is:

    ctags main.c

This command will generate a *tags* files in the current directory which includes the reference information the definition of functions in this *main.c*. If we open that *tags* file we can see that tags located in the left and file name located next to them. Also we need the right and valid extension of our source files, for example, the following command cannot generate a right tag:

    ctag main

# Basic
Use ctag to analyze all source files in specific file types:

    ctags *.c *.h

When we are editing *main.c* and want to look up the definition of some function (command in Vim):

    :ptag stdio.h

Then we will open an separate preview window showing the *stdio.h*. Sure when we finished we use the following command (in Vim):

    :pclose

or

    :pc

# Basic 2
Besides the *ptag* command, we can move our cursor on the function which we want to loop up and execute *Control+]*, then we will go to that function's definition.

More:

    tags // show the tags table we executed
    Control + T // tag go back
    tag // tag go forward

# Daily
For a big project with several subdirectories:

    ctags -R --exclude=*.js

For other external lib:

    ctags -R --exclude=*.js . ~/.rvm/xxx/gems/

Here we can see that *.* stands for the current directory and second one is the external lib address.

