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
