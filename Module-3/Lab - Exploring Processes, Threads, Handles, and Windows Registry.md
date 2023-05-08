# Lab - Exploring Processes, Threads, Handles, and Windows Registry

## Part 1: Exploring Processes

* Navigate to the SysinternalsSuite folder with all the extracted files.
* Open procexp.exe. Accept the Process Explorer License Agreement when prompted.
* The Process Explorer displays a list of currently active processes.
* To locate the web browser process, drag the Find Window's Process icon into the opened web browser window. Microsoft Edge was used in this example.

![image](https://user-images.githubusercontent.com/33444140/236879669-16ed285f-c8e5-4393-8b41-2055ff565a51.png)

* The Microsoft Edge process can be terminated in the Process Explorer. Right-click the selected process and select Kill Process. Click OK to continue

![image](https://user-images.githubusercontent.com/33444140/236880266-4010ad90-fabd-476b-9719-fdd026bd5c55.png)

The browser window got closed when we killed the process.

## Step 3: Start another process.

* Open a Command Prompt. (Start > search Command Prompt > select Command Prompt)
* Drag the Find Window's Process icon into the Command Prompt window and locate the highlighted Command Prompt process in Process Explorer.

![image](https://user-images.githubusercontent.com/33444140/236881958-99cd5d4e-ac22-47f6-83ea-5c0118878b31.png)

* The process for the Command Prompt is cmd.exe. Its parent process is explorer.exe process. The cmd.exe has a child process, conhost.exe.
* Navigate to the Command Prompt window. Start a ping at the prompt and observe the changes under the cmd.exe process.
![image](https://user-images.githubusercontent.com/33444140/236882406-fcd9611d-f5a3-4edb-863e-e580cc58737c.png)
