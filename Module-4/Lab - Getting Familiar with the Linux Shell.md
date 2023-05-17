## Lab - Getting Familiar with the Linux Shell

## Part 1: Shell Basics

### Step 1: Access the Command Line

* Log on to the CyberOps Workstation VM as the analyst using the password cyberops. The account analyst is used as the example user account throughout this lab.
* To access the command line, click the terminal icon located in the Dock, at the bottom of VM screen. The terminal emulator opens.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/5e48adc0-6c6e-4b1d-a36a-380d41d0ed30)

### Step 2: Display Manual Pages from the command line.

> You can display command line help using the man command. A man page, short for manual page, is a builtin documentation of the Linux commands. A man page provides detailed information about a given command
and all its available options.

* To learn more about the man page, type: `man man`

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/7dc6b554-3f0c-42b8-b778-432971984272)

    It contains Name, Synopsis, Descriptions, Examples, Overview, Defaults etc.
    
* Type q to exit the man page
* Use the `man` command to learn more about the `cp` command:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/725ec67c-b506-4732-b681-05f1e9f755b0)

* What is the function of the cp command?

      It copies files and dirctories
      
* What command would you use to find out more information about the pwd command? What is the function of the pwd command?
  
      We use man pwd command to find its info and it prints the name of current working directory
      
### Step 3: Create and change directories

In this step, you will use the change directory (cd), make directory (mkdir), and list directory (ls) commands.

* Type `pwd` at the prompt. What is the current directory?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/69800ae5-205e-49c4-be23-b6be112c77d8)

* Navigate to the `/home/analyst` directory if it is not your current directory. Type `cd /home/analyst`
* Type `ls -l` at the command prompt to list the files and folders that are in the current folder. Standing for list, the -l option displays file size, permissions, ownership, date of creation and more.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/0bd90e64-ad76-447f-97f3-3049edd60563)

* In the current directory, use the mkdir command to create three new folders: cyops_folder1, cyops_folder2, and cyops_folder3. Type `mkdir cyops_folder1` and press Enter. Repeat these steps to create cyops_folder2 and cyops_folder3.

* Type ls -l to verify that the folders have been created:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/ffe7ecd8-9b4a-4b83-95a2-6afb6393053b)

* Type `cd /home/analyst/cyops_folder3` at the command prompt and press Enter
* Which folder are you in now?
            
        cyops_folder3
*  Use the `mkdir` command to create a new folder named `cyops_folder4` inside the `cyops_folder3` folder

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/67e17c1b-ce7b-47a1-9044-7fe552b8d42f)

> Up to this point, we have been using full or absolute paths. Absolute path is the term used when referring
to paths that always start at the root (/) directory. It is also possible to work with relative paths. Relative
paths reduce the amount of text to be typed. To understand relative paths, we must understand the . and
.. (dot and double dot) directories. From the cyops_folder3 directory, issue a ls –la:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/127da959-4144-4b48-a298-4b1b5182b844)

> The -a option tells ls to show all files. Notice the . and .. listings shown by ls. These listings are used by
the operating system to track the current directory (.) and the parent directory (..) You can see the use of
the . and .. when using the cd command to change directories. Using the cd command to change the
directory to the . directory incurs no visible directory change as the . points to the current directory itself.

* Change the current directory to /home/analyst/cyops_folder3:
* Type `cd .`
* Changing the directory to the .. directory, will change to the directory that is one level up. This directory is also known as parent directory. Type `cd ..`

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/390716b6-510f-44ca-b1fb-c21458475ba9)

* What would be the current directory if you issued the `cd ..` command at `[analyst@secOps ~]$`?
* What would be the current directory if you issued the `cd ..` command at `[analyst@secOps home]$`?
* What would be the current directory if you issued the `cd ..` command at `[analyst@secOps /]$`?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/ad1141c4-cedf-4086-a196-7f02573a740b)

### Step 4: Redirect Outputs.

> Another powerful command line operator in Linux is known as redirect. Represented by the > symbol, this
operator allows the output of a command to be redirected to some location other the current terminal window
(the default).

* Use the cd command to change to the /home/analyst/ (~) directory
* Use the echo command to echo a message. Because no output was defined, echo will output to the current terminal window:
* Use the > operator to redirect the output of echo to a text file instead of to the screen:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/3b717b02-2aa6-441e-9c8c-e416e124fc2d)

* Notice, that even though the some_text_file.txt file did not exist, prior to the echo command, it was automatically created to receive the output generated by echo. Use the ls -l command to verify if the file was really created:
* Use the cat command to display the contents of the some_text_file.txt text file:
* Use the > operator again to redirect a different echo output of echo to the some_text_file.txt text file:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/8fe6cdb6-f7b6-4979-9e97-4cf2419732e7)

* Once again, use the cat command to display the contents of the some_text_file.txt text file:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/dd8b1bf0-d243-4145-a94b-6d3119e93177)

### Step 5: Redirect and Append to a Text File.

> Similar to the > operator, the >> operator also allows for redirecting data to files. The difference is that >>
appends data to the end of the referred file, keeping the current contents intact. Append a message to
the some_text_file.txt

* Use the cat command to display the contents of the some_text_file.txt text file after appending:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/0e6e62ba-c5d6-44c5-8b85-1d2539b088ca)

### Step 6: Work with hidden files in Linux.

> In Linux, files with names that begin with a ‘.’ (single dot) are not shown by default. While dot-files have
nothing else special about them, they are called hidden files because of this feature. Examples of hidden
files are .file5, .file6, .file7.

* Use ls -l to display the files stored in the analyst home directory.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/9466fabf-7bfe-4bad-8cb4-b6f41905fbb7)

* Use the ls -la command to display all files in the home directory of analyst, including the hidden files.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/a64e2973-7af2-41a2-81c2-726ff738d270)

* Type the man ls command at the prompt to learn more about the ls command.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/24a73e11-654e-4cd2-81ec-a9f06732399b)

* Use the down arrow key (one line at a time) or the space bar (one page at a time) to scroll down the page and locate the -a option used above and read its description to familiarize yourself with the `ls -a` command.

## Part 2: Copying, Deleting, and Moving Files

### Step 1: Copying Files

> The cp command is used to copy files around the local file system. When using cp, a new copy of the file
is created and placed in the specified location, leaving the original file intact. The first parameter is the
source file and the second is the destination. Issue the command below to copy some_text_file.txt from
the home directory to the cyops_folder2 folder

* Use the ls command to verify that some_text_file.txt is now in cyops_folder2:
* Use the ls command to verify that some_text_file.txt is also in the home directory

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/7d8c1302-3ac4-418f-b9c9-f9e41f80fbb2)

### Step 2: Deleting Files and Directories

* Use the rm command to remove files. Issue the command below to remove the file some_text_file.txt from the home directory. The ls command is then used to show that the file some_text_file.txt has been removed from the home directory:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/d0ce5b98-4712-4bb5-a0fb-6e40cc22a183)

* In Linux, directories are seen as a type of file. As such, the rm command is also used to delete directories but the -r (recursive) option must be used. Notice that all files and other directories inside a given directory are also deleted when deleting a parent directory with the -r option. Issue the command below to
delete the cyops_folder1 folder and its contents:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/3d81ca27-1d83-4366-9209-3977fd49b158)

### Step 3: Moving Files and Directories

* Moving files works similarly to copying files. The difference is that moving a file removes it from its original location. Use the mv commands to move files around the local filesystem. Like the cp commands, the `mv` command also requires source and destination parameters. Issue the command below to move the `some_text_file.txt` from `/home/analyst/cyops_folder2` back to the home directory:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/6905b8ec-ac2f-4de3-9b86-4e962c12976c)

* What are the advantages of using the Linux command line?

        Through Linux command line we can specify the filenames with pathnames and we can apply various operations such as copy,move,create and delete i.e. manipulating the files easily.
        
