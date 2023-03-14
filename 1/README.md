# codewithmosh.com-github-course
This is a course works of git course offered by special instructor (MOSH).

- Three levels of configurations:
    1- System: All users.
    2- Global: All repositories of current user.
    3- Local:  The current repository

- Define a new config:
    * git config --global user.name "Nabil Alhafez"
    * git config --global user.email nabil.alhfz98@gmail.com
    * git config --global core.editor "code --wait" 
      wait flag: is to tell the terminal to wait until we    
      close new vs code window
    * git config --global -e: to open the visual studio code
    * git config --global core.autocrlf input/true: 
      configuring the end of lines handling macos{input} and windows{true}.
    * git config --help VS git config -h
    * git init: for inialaizing a new git rerository
    - EXTRA:
    * For having a beauty color installing on mac: zsh with git plugin
    * For having a beauty color installing on windows: posh-git plugin
    * For deleting git folder: rm -rf .git

- Git Workflow:
    * 1- Changing in our files (Adding, Deleting, Editing, ...) : before staging.
        - For eg: create file1 & edit file2

    * 2- Adding files to staging area: git add file1 file2.

    * 3- Recording a state in our repository: git commit -m "Initial commit"

    * 4- The staging area has the last commit that has done or initially empty.

    * 5- Making changes : before staging.
        - For eg: delete file1
    
    * 6- Adding files to staging area again: git add file1.
        Explaining: here I've deleted the file and used git add file1 to stage the changes,
        it's normal as it is.
    
    * 7- Now Recording a complete state of our code in our repository: 
        git commit -m "Deleting file1"
    
    * 8- Each commit has: 
        - ID
        - Message
        - Date/Time
        - Author
        - Complete Snapshot

- Git Current Repository Info:
    * git status

- Extra:
    * write in file: echo world > file1.txt
    * append in file: echo world >> file1.txt

- Git Staging:
    * git add file1.txt           : add one file.
    * git add file1.txt file2.txt : add multiple files with a space between them.
    * git add *.txt               : add all files with extension txt.
    * git add .                   : add all files starting from the root of the current 
      folder recursively.

- To add more context when commiting we can drop the message for eg: git commit
    and git opens the default editor for us then we can add a short and long message
    have the following form:
    Short message.
    
    Long message.

- Best practice for wording is present tense => Fix the bug.

- Skipping Staging area: 
    * echo test >> file1.txt
    * git commit -a -m "Fix the bug the prevented the user from signin in" 
        EQUALS WITH
      git commit -am   "Fix the bug the prevented the user from signin in"

- Getting files in staging area:
    * git ls-files

- Getting files in staging area:
    * git ls-files

- Instead of deleting file with terminal or system command we can use the git delete file command which delete the file from our directory and from the staging area:
    * git rm <filename>
    * '' > file1.txt : creating a new empty file
    * mv file1.txt main.js in unix : moving file from <filesoruce> <filedestination>
    * git mv <file-soruce> <file-destination> : does the action on the git history and the directory on our system

- Ignoring some files with gitignore: 
    * mkdir logs && echo hello > logs/dev.log
    * echo logs/ > .gitignore 
    * code .gitignore 
    * As patterns we can add: the following 
        `logs/` : ignores a folder within the project root.
        `*.log` : ignores all files that has an extension of log.

- Removing a file from the staging/index area:
    * First of all, checking the files that are in the staging area by running:
        `git ls-files`
    * Secondly, we use a method that we already talked about it `git rm` 
      but using this method directly removing the the target from the system too, so
      we can get a help with the command `git rm` as following:
        `git rm -h`
    * Now, we see the options, we can call the function to remove one file as following:
        `git rm --cached <filesname.extension>`
    * If we are removing a directory we should apply it recursily 
        `git rm --cached -r <foldername>`


- Short status, to get a short summriazable status about the project we can run the following:
    `git status -s`
    * After running we should get something like: (MM, A, M OR ??): Which the first column represnts the staging area and the second column represents the working directory. Also the ?? represents the added files.
    We also have colors (Red & Green):  Red for modified unstaged files and green for staged files.


- Viewing Staged and Unstaged Changes:
    * `git diff --staged` : for viewing staged changes.
    * `git diff`          : for viewing unstaged changes from the working directory.


- Visual Diff Tools using VS-Code 
    * `git config --global diff.tool vscode`: global means apply for all of our repositories. with this command we are give a name (vscode) to our default diff tool
    * `git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"` :
        + --wait         : it tells the window to wait until we finish using the vscode.
        + --diff it      : tells the vscode that it's used for compairing for diffing.
        + $LOCAL, $REMOTE: These are placeholders for the old and new copy of the files.
    
    * Now, we should verify the settings that have been saved correclty.
    * `git config --global -e` : With this command we are able to edit the config of our global default editor which is vs-code in this case.
    * Now, we can use the default editor to view the differences, but we will do it through out the diff tool no the diff command but it applies the same logic and argument:
    * `git difftool --staged` : for viewing staged changes.
    * `git difftool`          : for viewing unstaged changes from the working directory.

- Viewing History:
    * `git log`                     : Getting comprehensive info about our history.
    * `git log --oneline`           : Getting summery info about our history.
    * `git log --oneline --reverse` : Getting summery reversed info about our history.

- Viewing a Commit:
    * `git show <commit-id>`
    * `git show HEAD`
    * `git show HEAD~1`                                                     : the number after the ~ is the offset from the head.
    * `git show HEAD~1:<full-path-of-the-file[for example: lib/main.dart]>` : to see the exact stored file in that commit.
    * `git ls-tree <commit-id OR HEAD>`                                     : to see the entier snapshot of the files which has the following: {Git Object, Git content ID, File name}
        + Git object are {Commits, Blobs(Files), Trees(Directories), Tags}


- Unstaging files (undoing git add)
    * `git restore --staged <file1.txt file2.txt . *.txt>`
    * How does the `git restore --staged` it takes a copy of the next env/last commit/last snapshot, if the file does exist in that env if not,it means that the file is added 
    and it will be deleted from the staging area and it will have the initaile state which is untracked file.


- Discarding Local Changes before staging: This is a dangerous action
    * `git clean -h` : For help.
    * `git clean -f` : For cleaning forcly.
    * `git clean -d` : For cleaning directories.
    * `git clean -fd`: Removes all untracked files.

- Restoring a File to an Earlier Version:
    * git rm file2.js
    * git restore file.js                 # Copies file.js from index to working directory  
    * git restore file1.js file2.js       # Restores multiple files in working directory 
    * git restore .                       # Discards all local changes (except untracked files)
    * git restore --source=HEAD~2 file.js # Restoring an earlier version of a file.
