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
