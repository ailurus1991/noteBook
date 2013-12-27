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

## Basic usage

Basic commit method:

    git add xxx.md
    git commit -m "some comments"

For log file, we can use:

    git log -p

Sure this is not friendly enough, so we can try [tig](https://github.com/jonas/tig)

Since git need us to add the file before commit every time, so sure we can use some tips here:

    git commit -a -m "some comment"

This way to add the changed files we've added previously default.

## Multiple lines comments

    git commit -a -v //Press Enter

Change the default comment editor

    git config --global core.editor vim

Actually it changed the file ~/.gitconfig. Sure we use a alias eventually:

    git config --global alias.ci "commit -a -v"

So we can use:

    git ci

to commit. See ~/.gitconfig for details.

# git-workflow

See something in .gitconfig file:

    ci = commit -a -v
    throw = reset --hard HEAD
    throwh = reset --hard HEAD^

Before use git commit, we can use:

    git diff

to check or decide commit or not. If we find that don't want to commit and undo the operation:

    git throw

Sure we can also roll back to the version before last commit operation:

    git throwh

Sometimes, we operated multiple files, and we just want to commit part of them. However, git throw will undo the whole operation, we use:

    git checkout hello.h

Then, all we will commit is files without hello.h.

*git stash*
this is a stack to store temporary changes, we can store all changes we made but not submitted and restore when we fixed a small bug.

    git stash
    //fixed the bugs
    git stash apply

Actually just like create a brand new/temp branch.

*branch*
create a new branch with different git logs:

    git checkout -b tmp

When we've finished the work and we want to delete the useless branch:

    git checkout -D tmp

Create a branch from previous version:

    git checkout faxxx -b tmp // faxxx is the version number

