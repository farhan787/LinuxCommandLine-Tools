# Unix and Linux Command Line Tools
       
## <img src="https://i.imgur.com/qdU0MQY.png" alt="drawing" width="40"/>  [Download PDF](https://drive.google.com/open?id=1EFYgDFmrbr0dYRzGsEO7E5vhZGFIGTAK)

### Symbols and Uses
1. **>** redirects standard output of a command to a file, overwriting previous content.
2. **>>** redirects standard output of a command to a file, appending new content to old content.
3. **<** redirects standard input to a command.
4. **|** redirects standard output of a command to another command.

### Some General terms and keywords
1. **sort**: sorts lines of text alphabetically.
2. **uniq**: filters duplicate, adjacent lines of text.
3. **grep**: searches for a text pattern and outputs it.
4. **sed** : searches for a text pattern, modifies it and outputs it.
5. **export** VARIABLE="Value" sets and exports an environment variable.
6. **USER** is the name of the current user.
7. **PS1** is the command prompt.
8. **HOME** is the home directory. It is usually not customised.
9. **PATH** returns a colon separated list of file paths. It is customised in advanced cases.
10. **env** returns a list of environment variables. <br />
    *e.g., env | grep PATH*

### Now Understanding above commands or keywords and even more

1. **pwd command**: *pwd* stands for 'print working directory'. It prints the current directory.
    ``` terminal
       $ pwd
    ```
    ![GitHub Logo](/screenshots/pwd.PNG)

1. **ls command**: *ls* stands for 'list directory content'. Display all the files and directories in the current directory.
 '-' this is known as a flag, we can add more specifications and properties to our commands using these flags like in case of *ls*. e.g.,
    ``` terminal
       $ ls -a -l -h -r 
    ```
    * This will print all the files and directories in the current directory but -a flag will help us to display the hidden  files and directories, -l helps us to show detailed format, -r shows in reverse order and -h for units of memory, B for Bytes etc.

       *  **You can also do like:**
    ``` terminal
       $ ls -alhr
    ```
    ![GitHub Logo](/screenshots/ls.PNG)
    
1. **cd command**: *cd* stands for 'change directory' and helps us to change the directory.
    ``` terminal
       $ cd games/
    ```
    ![GitHub Logo](/screenshots/cd.PNG)
    
1. **clear command**: *clear* is used to clear the console screen
    ``` terminal
       $ clear
    ```
    
1. **cp command**: *cp* is used to copy single or multiple files in current or another directory.
    ``` terminal
       $ cp add.c programs/
    ```
    add.c file will be copied to programs directory which is present in current directory.
    ![GitHub Logo](/screenshots/cp.PNG)

1. **mv command**: *mv* is used to move or rename single or multiple files.
    ``` terminal
       $ mv add.c interger_add.c 
    ```
    renaming add.c to integer_add.c
    
    ![GitHub Logo](/screenshots/mv_rename.PNG)
    
    ``` terminal
       $ mv add.c programs/
    ```
    moving add.c file to programs directory
    ![GitHub Logo](/screenshots/mv_move.PNG)
    
    
1. **cat command**: *cat* stands for 'concatenate and print files'. It displays all the content of a file.
    ``` terminal
       $ cat add.c
    ```
    It can be also used for copying and creating a new file and if the file exists and still we are using cat command to copy content then the content of the new file will be deleted and the copied content will be there. Below if the new_add.c exists before then it's content will be deleted and it'll have the copied content of add.c file.
    ``` terminal
       $ cat add.c > new_add.c
    ```
    **If you want contents of both files then use >> operator instead of >**
    ![GitHub Logo](/screenshots/cat.PNG)
    
1. **wc command**: wc stands for words, character, and it prints the number of lines, words and characters and file name of a file.
    ``` terminal
       $ wc script.py
    ```
    ![GitHub Logo](/screenshots/wc.PNG)
    
1. **sort command**: sorts the content of a file in alphabetical order.
    ``` terminal
       $ sort names.txt
    ```
    ![GitHub Logo](/screenshots/sort.PNG)
    
1. **Pipe (|)**: Pipe ‘|’ this takes the command as standard output on the left of it and pipes it as a standard input to the command on its right.
    ``` terminal
       $ env | grep PATH
    ```
    ![GitHub Logo](/screenshots/pipe.PNG)
    
1. **uniq command**: uniq stands for "unique" and filters out only adjacent, duplicate lines in a file and hence it will not remove those repeating lines which are not adjacent and are coming after some lines so to overcome this we can first sort the lines and then use the uniq command if we don’t want even a single line repeated.
    ``` terminal
       $ sort names.txt | uniq > sorted_names.txt
    ```
    ![GitHub Logo](/screenshots/uniq.PNG)
    
1. **grep command**: grep stands for "global regular expression print". It searches in a files for lines that match a pattern and returns the results. It is also case sensitive. Here, grep searches for "cout" in code.cpp file and print all lines which contains it.
    ``` terminal
       $ grep cout code.cpp
    ```
    **Tip:** *grep -i flag will remove the case sensitivity of the pattern being searched.*
    ![GitHub Logo](/screenshots/grep.PNG)
    
1. **sed command**: sed stands for "stream editor". It accepts standard input and modifies it based on an expression, before displaying it as output data. It is similar to "find and replace".
    <br />

    **Let's look at the expression 's/snow/rain/':**
        <br />
        
      * s: stands for "substitution". It is always used when using sed for substitution.
      * snow: the search string, the text to find.
      * rain: the replacement string, the text to add in place.
        ``` terminal
           $ sed 's/snow/rain/' forests.txt
        ```
        but note one thing it will only replace the first snow word with rain if you want to do it in the whole file then you have to use 
        ``` terminal
           $ sed 's/snow/rain/g' forests.txt
        ```
    ![GitHub Logo](/screenshots/sed.PNG)
    
1. **nano command**: nano is a command line text editor. It works just like a desktop text editor like TextEdit or Notepad, except that it is accessible from the command line and only accepts keyboard input. It can edit or create a new file for you.
    ``` terminal
       $ nano hello_world.js
    ```
       1. Ctrl + O, saves a file, O stands for output
       2. Ctrl + X, exits the nano program, X stands for exit
       3. Ctrl + G, opens a help menu
    <br />
    
    **Note:** *Similarly, there is vim which can be accessed by vi command but it is operated differently*

<br />

### Bash Profile file
bash_profile is the name of file used to store environment settings. It is commonly called the "bash profile". When a session starts, it will load the contents of the bash profile before executing commands.
``` terminal
   $ cat ~/.bash_profile
   $ nano ~/.bash_profile
```
![GitHub Logo](/screenshots/bash_profile.PNG)
    
   1. The ~ represents the user's home directory.
   1. The . indicates that this file hidden file. A dot is used for hidden file
   1. The name ~/.bash_profile is important, since this is how the command line recognises the bash profile.
   1. The command nano ~/.bash_profile opens up ~/.bash_profile in nano.
   1. The text echo "Welcome, Jane Doe" creates a greeting in the bash profile, which is saved. It tells the command line to echo the string "Welcome, Jane Doe" when a terminal session begins.
   1. The command source ~/.bash_profile activates the changes in ~/.bash_profile for the current session.
``` terminal
   $ source ~/.bash_profile
```
* Instead of closing the terminal and needing to start a new session, source makes the changes available right away in the session we are in.
<br />

**Note:** *Similarly, there is .bashrc file which is available in some computers. You can use anyone of them just make sure which file dominates.*

<br />

### Aliases
You can create shortcuts using alias command for long and frequently used commands and then you can use the small keywords instead of writing a long command and of course you can separate multiple commands using semicolons(;) like in second example.
* I frequently use second one to reach my desktop easily by only pressing f
``` terminal
   $ alias cls='clear'
   $ alias f='cd ~/Desktop/'
```

``` terminal
   $ alias hide='defaults write com.apple.finder CreateDesktop false; killall Finder'
   $ alias show='defaults write com.apple.finder CreateDesktop true; killall Finder'
```
![GitHub Logo](/screenshots/alias.PNG)
    
   * Using second command you can hide all your Desktop folders and files and no body will be able to see your stuff. You can undo this using third command. But this is only valid for Apple Mac users.
   <br />
   
   **Note:** 
   * **alias cls = 'clear' is wrong only cls='clear' will work.**
   * **You can save all your aliases into bash_profile file if you want to make them permanent.**


<br />

### Environment
Each time we launch the terminal application, it creates a new session. The session immediately loads settings and preferences that make up the command line environment. We can configure the environment to support the commands and programs we create. This enables us to customise greetings and command aliases, and create variables to share across commands and
programs.

<br />

**env command**: The env command stands for "environment", and returns a list of the environment variables for the current user. Here, the env command returns a number of variables, including PATH, PWD, PS1, and HOME.
``` terminal
   $ env
```
![GitHub Logo](/screenshots/env.PNG)
    
You can also try
``` terminal
   $ env | grep PATH
```
This will print the PATH environment vairable from the environment using grep command. I hope now you are able to use these commands simultaneously. *Congratulate yourself!!*.

#### Environment Variables
Environment variables are variables that can be used across commands and programs and hold information about the environment.
Some of the environment variables are given below, rest you can explore on your own.

1. **USER variable**: export USER="Farhan" sets the environment variable USER to a name "Farhan". Usually the USER variable is set to the name of the Computer's owner.
    ``` terminal
       $ export USER="Farhan"
       $ echo $USER
    ```
    ![GitHub Logo](/screenshots/ps1.PNG)
   * The line export makes the variable to be available to all child sessions initiated from the session you are in. This is  a way to make the variable persist across programs.
   * At the command line, the command echo $USER prints the value of the variable.
   <br />
   
   **Note that $ is always used when we are using an environmental**. Here, the command echo $USER prints the name set for the variable.

   
2. **PS1 variable**: PS1 is a variable that defines the makeup and style of the command prompt.
    ``` terminal
       $ export PS1="I am developer >> "
        I am developer >> ls
    ```
export PS1="I am developer >> " will change the styling of your command prompt to this.
![GitHub Logo](/screenshots/ps1.PNG)
    

3. **HOME variable**: The HOME variable is an environment variable that displays the path of the home directory.
    ``` terminal
       $ echo $HOME
    ```
![GitHub Logo](/screenshots/home.PNG)
    

4. **PATH variable**: PATH is an environment variable that stores a list of directories separated by colons(:). Each directory contains scripts for the command line to execute. The PATH variable simply lists those directories that contain scripts.
``` terminal
   $ echo $PATH
```
For example, many commands we've learned are scripts stored in the /bin directory. 
> This is the script that is executed when you type the pwd command. /bin/pwd.
<br />

> This is the script that is executed when you type the ls command.  /bin/ls
    ![GitHub Logo](/screenshots/path.PNG)

## Some tips
   ![GitHub Logo](/screenshots/linux-file-system.jpg)
   * You can also use man command to know or gain information about any command including the flags that you can use with that command
      ``` terminal
         $ man cat
      ```
   * Single dot (.) in Unix or Linux is used for current directory
      ``` terminal
         $ ls .
      ```
   * Double dots (..) are used for one level up directory
       ``` terminal
          $ ls ../
       ```

