#Create directory tree
Sometimes we need to create a directory tree without creating them one by one:

    mkdir -p tmp/a/b/c

Also we can use command to create them simply:

    mkdir -p project/{lib/ext,bin,src,doc/{html,pdf,texs}}

#Extract achieve in different directory
Just use ``-C`` in the command:

    tar xvf -C tmp/a/b/c newarc.tar.gz // here the tmp/a/b/c is the goal directory we want to extract

#Combine two or more commands together
### First part right
The second command will be executed only when the first one returned the right value:

    cd /tmp/a/b/c && data

The second command will be execute only if when the first one returned the wrong value:

    cd /tmp/a/b/c || mkdir -p /tmp/a/b/c  // Here if we can not find the goal direcotory, we will create that one.


