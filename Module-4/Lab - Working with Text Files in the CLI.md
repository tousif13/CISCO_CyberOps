## Lab - Working with Text Files in the CLI

## Part 1: Graphical Text Editors

> Text editors are one of the oldest categories of applications created for computers. Linux, like many other
operating systems, has many different text editors, with various features and functions. Some text editors
include graphical interfaces, while others are only usable via the command line. Each text editor includes a
feature set designed to support a specific work scenario. Some text editors focus on the programmer and
include features such as syntax highlighting, bracket matching, find and replace, multi-line Regex support,
spell check, and other programming-focused features

### Step 1: Open SciTE from the GUI

* Log on to the CyberOps VM as the user analyst using the password cyberops. The account analyst is used as the example user account throughout this lab.
* On the top bar, navigate to Applications > CyberOPS > SciTE to launch the SciTE text editor

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/220a510e-9650-4623-9adc-41378b0d9166)

SciTE is simple but includes a few important features: tabbed environment, syntax highlighting and more.
Spend a few minutes with SciTE. In the main work area, type or copy and paste the text below:

    “Space, is big. Really big. You just won't believe how vastly, hugely, mindbogglingly big it is. I mean, you may think it's a long way down the road to the chemist, but that's just peanuts to space.”

* Click File > Save to save the file. Notice that SciTE attempts to save the file to the current user’s home directory, which is analyst, by default. Name the file space.txt and click Save.
* Close SciTE by clicking the X icon on the upper right side of the window and then reopen SciTE.
* Click File > Open… and search for the newly saved file, space.txt.
* Question: Could you immediately find space.txt?
      
      No
* Even though SciTE is looking at the correct directory (/home/analyst), space.txt is not displayed. This is because SciTE is looking for known extensions and .txt is not one of them. To display all files, click the dropdown menu at the bottom of the Open File window and select All Files (*)

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/0a98e277-d5f2-49b6-8b10-e80f21ec7508)

* Select space.txt to open it.
* Close space.txt when finished.

### Step 2: Open SciTE from the Terminal.

* Alternatively, you can also open SciTE from the command line. Click the terminal icon located in the Dock at the bottom of the desktop. The terminal emulator opens.
* Type ls to see the contents of the current directory. Notice space.txt is listed. This means you do not have to provide path information to open the file.
* Type scite space.txt to open SciTE. Note that this will not only launch SciTE in the GUI, but it will also automatically load the space.txt text file that was previously created. `[analyst@secOps ~]$ scite space.txt`

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/b5471405-a9b5-426f-ab63-a5558dd445b3)

* Notice that while SciTE is open on the foreground, the terminal window used to launch it is still open in the background. In addition, notice that the terminal window used to launch SciTE no longer displays the prompt.
* Close this instance of SciTE by either clicking the X icon as before, or by switching the focus back to the terminal window that launched SciTE and stopping the process. You can stop the process by pressing CTRL+C.
* Close SciTE and move on to the next section. 

## Part 2: Command Line Text Editors

While graphical text editors are convenient and easy to use, command line-based text editors are very important in Linux computers. The main benefit of command line-based text editors is that they allow for text file editing from a remote shell on a remote computer.

Consider the following scenario. A user must perform administrative tasks on a Linux computer but is not sitting in front of that computer. Using SSH, the user starts a remote shell to the aforementioned computer. Under the text-based remote shell, the graphical interface may not be available which makes it impossible to rely on graphical text editors. In this type of situation, text-based text editors are crucial. 

The Cisco CyberOps Workstation VM includes a few command line-based text editors. This course focuses on nano.

Due to the lack of graphical support, nano (or GNU nano) can be controlled solely through the keyboard.
CTRL+O saves the current file; CTRL+W opens the search menu. GNU nano uses a two-line shortcut bar at the bottom of the screen, where a number of commands for the current context are listed. After nano is open, press CTRL+G for the help screen and a complete list.

* In the terminal window, type `nano space.txt` to open the text file created in Part 1.
* nano will launch and automatically load the space.txt text file. While the text may seem to be truncated or incomplete, it is not. Because the text was created with no return characters and line wrapping is not enabled, by default, nano is displaying one long line of text.
Use the Home and End keyboard keys to quickly navigate to the beginning and to the end of a line, respectively.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/a6ba3141-efef-4160-8a96-834e2c6a3e4c)

* What character does nano use to represent that a line continues beyond the boundaries of the screen?

        $

* As shown on the bottom shortcut lines, CTRL+X can be used to exit nano. nano will ask if you want to save the file before exiting (‘Y’ for Yes, or N for ‘No’). If ‘Y’ is chosen, you will be prompted to press enter to accept the given file name, or change the file name, or provide a file name if it is a new unnamed document.
* To control nano, you can use CTRL, ALT, ESCAPE or the META keys. The META key is the key on the keyboard with a Windows or Mac logo, depending on your keyboard configuration.
Navigation in nano is very user friendly. Use the arrows to move around the files. Page Up and Page Down can also be used to skip forward or backwards entire pages. Spend some time with nano and its help screen. To enter the help screen, press CTRL+G. Press q to quit the help screen and return to
document editing in nano.

## Part 3: Working with Configuration Files

### Step 1: Locating Configuration Files

> The program author defines the location of configuration for a given program (service or application). Because
of that, the documentation should be consulted when assessing the location of the configuration file.
Conventionally however, in Linux, configuration files that are used to configure user applications are often
placed in the user’s home directory while configuration files used to control system-wide services are placed
in the /etc directory. Users always have permission to write to their own home directories and are able to
configure the behavior of applications they use

* Use the `ls` command to list all the files in the `analyst` home directory:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/186461c5-82b3-4ba9-bca8-5b551440bb3e)

* While a few files are displayed, none of them seem to be configuration files. This is because it is convention to hide home-directory-hosted configuration files by preceding their names with a “.” (dot) character
* Use the `ls` command again but this time add the `–a` option to also include hidden files in the output:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/517f84ad-df26-4db5-96f1-574d50a3453f)

* Use cat command to display the contents of the .bashrc file. This file is used to configure user-specific terminal behavior and customization

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/971133ee-6d3c-469e-879d-425cfda8018b)

> Do not worry too much about the syntax of .bashrc at this point. The important thing to notice is that
.bashrc contains configuration for the terminal. For example, the line PS1='\[\e[1;32m\][\u@\h
\W]\$\[\e[0m\] ' defines the prompt structure of the prompt displayed by the terminal:
[username@hostname current_dir] followed by a dollar sign, all in green. A few other configurations
include shortcuts to commands such as ls and vi. In this case, every time the user types ls, the shell
automatically converts that to ls –color to display a color-coded output for ls (directories in blue, regular
files in grey, executable files in green, etc.)

> While configuration files related to user applications are conventionally placed under the user’s home
directory, configuration files relating to system-wide services are place in the /etc directory, by
convention. Web services, print services, ftp services, and email services are examples of services that
affect the entire system and of which configuration files are stored under /etc. Notice that regular users do
not have writing access to /etc. This is important as it restricts the ability to change the system-wide
service configuration to the root user only.

* Use the `ls` command to list the contents of the `/etc` directory:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/33f7c4d9-185d-49fd-9d51-05bffcc72cfc)

* Use the `cat` command to display the contents of the `bash.bashrc` file:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/9c49ae64-31fd-43ff-9a2e-461e5c928270)

> The syntax of bash.bashrc is out of scope of this course. This file defines the default behavior of the
shell for all users. If a user wants to customize his/her own shell behavior, the default behavior can be
overridden by editing the .bashrc file located in the user’s home directory. Because this is a system-wide
configuration, the configuration file is placed under /etc, making it editable only by the root user.
Therefore, the user will have to log in as root to modify bash.bashrc.

### Step 2: Editing and Saving Configuration files

Let’s edit .bashrc to change the color of the shell prompt from green to red for the analyst user.

* First, open SciTE by selecting Applications > CyberOPS > SciTE from the tool bar located in the upper portion of the Cisco CyberOPS VM screen.
* Select File > Open to launch SciTE’s Open File window.
* Because .bashrc is a hidden file with no extension, SciTE does not display it in the file list. If the Location feature is not visible in the dialog box, Change the type of file shown by selecting All Files (*) from the type drop box, as shown below. All the files in the analyst’s home directory are shown.
* Select .bashrc and click Open.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/20fdd84f-bb78-4834-8d83-f209f335da1b)

* `Locate 32 and replace it with 31`. 32 is the color code for `green`, while `31 represents red`
* Save the file by selecting File > Save and close SciTE by clicking the X icon.
* Click the Terminal application icon located on the Dock, at the bottom center of the Cisco CyberOPS VM screen. The prompt should appear in red instead of green.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/4f6e1898-6136-4ae5-8a90-feafee785c7f)

* The same change could have been made from the command line with a text editor such as nano. From a new terminal window, type nano .bashrc to launch nano and automatically load the .bashrc file in it:
* Change 31 to 33. 33 is the color code to yellow.
* Press CTRL+X to save and then press Y to confirm. The text editor nano will also offer you the chance to change the filename. Simply press ENTER to use the same name, .bashrc.
* The text editor nano will end, and you will be back on the shell prompt. This time reload the bash terminal by entering the command bash in the terminal. The prompt should now appear in yellow instead of red.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/941591e8-1ada-4180-be3a-7431d29ffad3)

### Step 3: Editing Configuration Files for Services

> System-wide configuration files are not very different from the user-application files. nginx is a lightweight
web server that is installed in the Cisco CyberOPS Workstation VM. nginx can be customized by changing
its configuration file, which is located in /etc/nginx.

* First, open nginx’s configuration file in a nano. The configuration file name used here is custom_server.conf. Notice below that the command is preceded by the sudo command. After typing
nano include a space and the -l switch to turn on line-numbering. 

`sudo nano -l /etc/nginx/custom_server.conf`

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/4158e9bd-d3da-455c-a6b1-840cf4248a23)

* While the configuration file has many parameters, we will configure only two: the port nginx listens on for incoming connections, and the directory it will serve web pages from, including the index HTML homepage file.
* Notice that at the bottom of the window, above the nano commands, the line number is highlighted and listed. On line 39, change the port number from `81 to 8080`. This will tell nginx to listen to HTTP requests on port `TCP 8080`.
* Next, move to line 47 and change the path from `/usr/share/nginx/html/` to `/usr/share/nginx/html/text_ed_lab/`
* Press CTRL+X to save the file. Press Y and then ENTER to confirm and use the custom_server.conf as the filename.
* Type the command below to execute nginx using the modified configuration file:

`sudo nginx -c custom_server.conf`

* Click the web browser icon on the Dock to launch Firefox.
* On the address bar, type 127.0.0.1:8080 to connect to a web server hosted on the local machine on port 8080. A page related to this lab should appear

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/32ee4e37-5de5-4589-8787-0982139060b3)

* After successfully opening the nginx homepage, look at the connection message in the terminal window. What is the error message referring to?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/2ba0b5ee-fb09-4867-b8fb-4ec2a445dfc2)

* To shut down the nginx webserver, press ENTER to get a command prompt and type the following
command in the terminal window:

`sudo pkill nginx`

* You can test whether the nginx server is indeed shut down by first clearing the recent history in the web browser, then close and re-open the web browser, then go to the nginx homepage at 127.0.0.1:8080. Does the web page appear?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/bdfc330c-1a37-4044-aae3-caf2f3efd8c7)
