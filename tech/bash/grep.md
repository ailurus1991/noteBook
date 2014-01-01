Its name comes from *ed* command (text editor) g/re/p (global / regular expression / print). 

We can use *grep* in Vim command mode, which means we filter the string *log* (regular expression):

    :g/^log/p

# Basic
Use *grep* in text file with regular expression:

    grep ^log test.txt // if we don't set the test.txt, grep will execute in our next keyboard input

    grep log log.txt // basic grep usage, print the string contains *log*
    grep -i log log.txt // print the string contains *log* and *Log* and others 
    grep -w log log.txt // print the whole word, not just a word contains the *log*

Control the beginning or ending characters:

    grep '\<log' log.txt // will prints the word start with *log*, such as: log, logsys
    grep 'log>\>log' lot.txt // will prints the word end with *log*, such as: log, syslog

# More
Here we can use *-v* parameter to filter the string we don't want to see:

    grep -v sys // string contain *sys* will not be printed, such as *syslog* or *logsys* will be ignored

Print the process name with specific string:

    ps aux | grep cron | grep -v color | awk '{print $2}' 
