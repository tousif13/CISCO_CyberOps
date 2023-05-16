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

