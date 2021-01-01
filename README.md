# Gitlet - version-control system
Smaller and simpler version-control system that mimics some of the basic features of [Git](http://git-scm.com/).

## Features 
* init
    * `java gitlet.Main init`
    * Initializes Gitlet version-control system in the current directory.
* add
    * `java gitlet.Main add [file name]`
    * Adds a copy of the file to the staging area, marking it for inclusion in the next commit. 
* commit 
    * `java gitlet.Main commit [message]`
    * Saves a snapshot of all the files in the staging area, so they can be referred back at a later time.
* rm
    * `java gitlet.Main rm [file name]`
    * If the file is included in the current commit, stages it for removal and deletes the file; and unstages the file, if the file is staged for addition. 
* log
    * `java gitlet.Main log`
    * Displays information about all the commits made before and starting at current commit.
* global-log
    * `java gitlet.Main global-log`
    * Displays information about all the commits ever made.
* find
    * `java gitlet.Main find [commit message]`
    * Prints out the id of all commits that have the given commit message.
* status
    * `java gitlet.Main status`
    * Displays the current state of staging area and the current working directory. 
* checkout
    * `java gitlet.Main checkout -- [file name]`
        * Takes the version of file in the current/HEAD commit and puts it in the working directory, overwriting the file that's already there.    
    * `java gitlet.Main checkout [commit id] -- [file name]`
        * Takes the version of file in the commit with the given id and puts it in working directory, overwriting the file that's already there. 
    * `java gitlet.Main checkout [branch name]`
        * Takes all the files from the commit at HEAD of the given branch and puts it in the working directory, overwriting the files that are already there. 
* branch
    * `java gitlet.Main branch [branch name]`
    * Creates a new branch making it point to the current commit node.
* rm-branch
    * `java gitlet.Main rm-branch [branch name]`
    * Deletes the branch with the given branch name.
* reset
    * `java gitlet.Main reset [commit id]`
    * Checks out all the files present in the commit with the given commit id. 
* merge
    * `java gitlet.Main merge [branch name]`
    * Takes all the files in the current commit, compares it with all the files in the commit pointed to by the head of the branch with the given branch name and integrates the current branch and branch with the given name into a single branch merging conflicts along the way.

If you ever find any of the listed features above confusing, you can refer [Git Documentation](https://git-scm.com/doc) as all of these commands are programmed to directly mimic some of Git's features.
## How To Use
To run this application on your local computer, you can simply clone this repository and start to play around with the features listed above.

From your command line:
```bash
# Clone this repository
$ git clone git@github.com:DirajThajali/Gitlet.git

# Compile and Initialize Gitlet in the current working directory
$ javac gitlet/*.java
$ java gitlet.Main init
```

Now, you can interact with all the commands listed below init. 
Here are few examples.
```bash
$ touch f.txt   # create a file and add some text to it.
$ java gitlet.Main status   # f.txt is currently untracked
=== Branches ===
*master

=== Staged Files ===

=== Removed Files ===

=== Modifications Not Staged For Commit ===

=== Untracked Files ===
f.txt

$ java gitlet.Main add f.txt    
$ java gitlet.Main status   # f.txt is now marked for inclusion in next commit
=== Branches ===
*master

=== Staged Files ===
f.txt

=== Removed Files ===

=== Modifications Not Staged For Commit ===

=== Untracked Files ===

$ java gitlet.Main commit "added f.txt"    # creating a commit
$ java gitlet.Main log   # As you can see, the commit we just made is in the list. By default, first commit is made when we initiliaze gitlet directory.
===
commit 793ce3e6a940a38689db1b297335e522b0c0526a
Date: Thu Dec 31 12:18:13 2020 -0800
added f.txt

===
commit 45713c733ebe312565270f94e8c58f46c50acaeb
Date: Wed Dec 31 16:00:00 1969 -0800
initial commit

```   
These are only few features of my version-control system Gitlet. Feel free to mess around with rest of the commands as well!