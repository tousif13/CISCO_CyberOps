# Using Windows Powershell

## Part 1: Access PowerShell console

* Click Start. Search and select powershell.
* Click Start. Search and select command prompt.

## Part 2: Explore Command Prompt and PowerShell commands

* Enter dir at the prompt in both windows.
* Question: What are the outputs to the dir command?

![image](https://user-images.githubusercontent.com/33444140/236898584-84292a4b-af52-45c0-8168-f57358e8fc8c.png)

* Try another command that you have used in the command prompt, such as ping, cd, and ipconfig.
* Question: What are the results?

![image](https://user-images.githubusercontent.com/33444140/236898894-196745b5-d51c-4480-83f1-644b7f871eb1.png)

![image](https://user-images.githubusercontent.com/33444140/236899048-fcf81652-86a1-4051-99e9-1ad1263df5d9.png)

## Part 3: Explore cmdlets

* PowerShell commands, cmdlets, are constructed in the form of verb-noun string. To identify the PowerShell command to list the subdirectories and files in a directory, enter Get-Alias dir at the PowerShell prompt.

![image](https://user-images.githubusercontent.com/33444140/236899391-750b9810-dc12-4daf-bb11-9ac4caf26a50.png)

* Close the Command Prompt window when done

## Part 4: Explore the netstat command using PowerShell.

* At the PowerShell prompt, enter `netstat -h` to see the options available for the `netstat` command.

![image](https://user-images.githubusercontent.com/33444140/236899591-0732738c-7c69-4001-83b2-f972a6e730d6.png)

* To display the `routing table with the active routes`, enter `netstat -r` at the prompt.

![image](https://user-images.githubusercontent.com/33444140/236899890-5952329f-bbf7-4828-9fad-4f2d0a6ad3f8.png)

* Open and run a second PowerShell with elevated privileges. Click Start. Search for PowerShell and rightclick Windows PowerShell and select Run as administrator. Click Yes to allow this app to make changes to your device.

* The netstat command can also display the processes associated with the active TCP connections. Enter the `netstat -abno` at the prompt.

![image](https://user-images.githubusercontent.com/33444140/236900315-09867273-7dbc-4f65-81d8-bb44b1751c35.png)

* Open the Task Manager. Navigate to the Details tab. Click the PID heading so the PID are in order.
* Select one of the PIDs from the results of netstat -abno. PID `5172` is used in this example.
* Locate the selected PID in the Task Manager. Right-click the selected PID in the Task Manager to open the Properties dialog box for more information.

![image](https://user-images.githubusercontent.com/33444140/236900882-aa6e12e4-4c24-41db-959d-05214553e5e5.png)

![image](https://user-images.githubusercontent.com/33444140/236901034-42d6e7fb-d5e0-4a5f-91d5-b727c09449a5.png)

* We will get the Type of file, Name, Username, Status information.

## Part 5: Empty recycle bin using PowerShell.

PowerShell commands can simplify management of a large computer network. For example, if you wanted to implement a new security solution on all servers in the network you could use a PowerShell command or script to implement and verify that the services are running. You can also run PowerShell commands to simplify actions that would take multiple steps to execute using Windows graphical desktop tools.

* Open the Recycle Bin. Verify that there are items that can be deleted permanently from your PC. If not, restore those files.

![image](https://user-images.githubusercontent.com/33444140/236902151-77896354-67d6-4419-a101-7c192f461745.png)

* In a PowerShell console, enter `clear-recyclebin` at the prompt.

![image](https://user-images.githubusercontent.com/33444140/236902321-27017235-6e83-407d-a28f-57c5dcf39e02.png)

What happened to the files in the Recycle Bin?
  
  It got deleted

![image](https://user-images.githubusercontent.com/33444140/236902450-cdad63cd-ce84-402b-8ab8-b291817eabf8.png)
