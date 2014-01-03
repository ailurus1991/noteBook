# Background Concept
* 1 --> standard output
* 2 --> standard error output
* 0 --> standard input

**update 01/03/2013**:
all these definitions are in <unistd.h>
* 1 --> STDIN_FILENO
* 2 --> STDOUT_FILENO
* 0 --> STDERR_FILENO


# Basic Usage
## Right Redirection >
### Redirect to file

    ls >output.txt // standard output
    ls xxx 2>output.txt // standard error output

Here if don't set parameter in the redirection signal, the default value is *1*, which means the standard output. So, the first one is same as:

    ls 1>output.txt

We can also use just one command to get:

    ls >output.txt 2>&1

*NOTE:* the execute order is right-left, which means we set *redirect standard error output to standard output* firstly, and then just use redirect as usual. So then we can redirect the standard I/O and standard error message to standard error output.

But, we can use a better and convenient one:

    ls &>output.txt

### Combine
Combine two or more files with using *cat* command:

    cat file1 file2>file3 // file3 should contain the content of file1 and file2

Another way to combine two files is append one to another:

    cat file1 >>file2 // the content in file1 will be appended in the end of file2

*NOTE:* once we use *>* command, the redirected file will be created from new. So we can use *>newFile.txt* to create a new file or clean the content of one file.
*NOTE(TESTED):* In OS X 10.9, *>newFile* will acted as *read A*.

### Example

    #!/usr/bin/env bash
    >output.txt
    for dir in /bin/usr /usr/bin
    do
        ls $dir &>>output.txt
    done

## Left Redirection <
### Read
For basic keyboard input, we can use:

    read A
    // type something using keyboard
    echo $A
to get get the keyboard's input and store the value into variable *A*.

If we want to redirect a file to this variable:

    read B <input.txt
