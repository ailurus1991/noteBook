# init

Sometimes need to setup global info:

    git config --global user.name "ailurus1991"
    git config --global user.email "pandachow19910411@gmail.com"

Which will generate a .gitconfig file in our home directory.

Initialize the git configure file in current directory

    git init

This will generate a hidden directory .git/ in current directory.

Checking current git status, for example, we can use this command to check if some files are tracked or not.

    git check

# Basic usage

Basic commit method:

    git add xxx.md
    git commit -m "some comments"

For log file, we can use:

    git log -p

Sure this is not friendly enough, so we can try [tig](https://github.com/jonas/tig)

Since git need us to add the file before commit every time, so sure we can use some tips here:

    git commit -a -m "some comment"

This way to add the changed files we've added previously default.

# Multiple lines comments

    git commit -a -v \Press Enter

Change the default comment editor

    git config --global core.editor vim

Actually it changed the file ~/.gitconfig. Sure we use a alias eventually:

    git config --global alias.ci "commit -a -v"

So we can use:

    git ci

to commit. See ~/.gitconfig for details.
