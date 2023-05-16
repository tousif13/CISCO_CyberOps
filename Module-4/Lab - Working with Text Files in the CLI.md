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
* What character does nano use to represent that a line continues beyond the boundaries of the screen?

        $

* As shown on the bottom shortcut lines, CTRL+X can be used to exit nano. nano will ask if you want to save the file before exiting (‘Y’ for Yes, or N for ‘No’). If ‘Y’ is chosen, you will be prompted to press enter to accept the given file name, or change the file name, or provide a file name if it is a new unnamed document.
* To control nano, you can use CTRL, ALT, ESCAPE or the META keys. The META key is the key on the keyboard with a Windows or Mac logo, depending on your keyboard configuration.
Navigation in nano is very user friendly. Use the arrows to move around the files. Page Up and Page Down can also be used to skip forward or backwards entire pages. Spend some time with nano and its help screen. To enter the help screen, press CTRL+G. Press q to quit the help screen and return to
document editing in nano.

