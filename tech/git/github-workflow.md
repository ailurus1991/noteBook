# fork

First we need fork with clone command to our local disk:

    git clone http://xxxxxxxx.git


# basic workflow

A good way is doing something on our another remote repository to track original master repository:

    git remote add upstream https://github.com/xxx/xxxxx.git // add other's original master address
    git remote -v // display the current statues of remote repository

Before we begin developing, we should fetch the newest code to our local master branch:

    git pull upstream master // fetch the newest code from upstream:master to origin:master

Also we shouldn't change on our own master branch, so we create a new branch:

    git checkout -b translating // add a new working branch called 'translating'

When we finish our development, we should fetch other contributors' code and test with our changes together:

    git pull upstream master // as previous operation
    git checkout translating // change our current working branch from master
    git rebase master // rebase the newest code from local master branch to our working branch (translating)

Then after the testing, we should commit and push:

    git ci // create a new version with comments
    git push origin translating // push the newest code in local branch (translating) to our remote origin repository in github

After than we can pull request at github.com *translating* <-> *master*

### for original author

Create a remote repository for the contributor:

    git remote add contributor1 git@gtihub.com:contributor1/xxx.git // add a remote repository for the contributor1
    git checkout -b testContributor1 // create a local branch for testing
    git pull contributor1 translating // pull the contributor1:translating to local origin:testContributor1

After the test part, the contributor can merge the contributor1:translating to the origin:master:

    git checkout master // switch to the origin master branch
    git merge testContributor1 // merge the testContributor1 (contributor1:translating) to the origin:master
    git push origin master // END

### for contributor

After get the notice that the author merged the branch, he can delete all temp work:

    git checkout master // switch to the master branch
    git push origin :translating // push without the translating (meas delete the translating)
    git branch -D translating // delete the local branch

So the only thing we do in our master branch is synchronization:

    git pull upstream master

