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

PING.exe popped up when using the PING command

* As you review the list of active processes, you find that the child process conhost.exe may be suspicious. To check for malicious content, right-click conhost.exe and select Check VirusTotal. When prompted, click Yes to agree to VirusTotal Terms of Service. Then click OK for the next prompt.

* Expand the Process Explorer window or scroll to the right until you see the VirusTotal column. Click the link under the VirusTotal column. The default web browser opens with the results regarding the malicious content of conhost.exe

![image](https://user-images.githubusercontent.com/33444140/236883360-2d01b429-ad09-478a-8e9d-3ae8892427ed.png)

* Right-click the cmd.exe process and select Kill Process.Question: What happened to the child process conhost.exe?

![image](https://user-images.githubusercontent.com/33444140/236883512-855083cf-4e8c-4c8e-83f7-6865455caa86.png)

* const.exe also got killed with cmd.exe

## Part 2: Exploring Threads and Handles
In this part, you will explore threads and handles. Processes have one or more threads. A thread is a unit of execution in a process. A handle is an abstract reference to memory blocks or objects managed by an operating system. You will use Process Explorer (procexp.exe) in Windows SysInternals Suite to explore the threads and handles. Step 1: Explore threads.

* Open a command prompt
* In Process Explorer window, right-click conhost.exe and Select Properties..... Click the Threads tab to view the active threads for the conhost.exe process. Click OK to continue if prompted by a warning dialog box.
![image](https://user-images.githubusercontent.com/33444140/236884228-2bd266a2-e65d-4a95-a745-45c7a410b249.png)

* Examine the details of the thread. What type of information is available in the Properties window?

        Version, Build Time, Parent, User, VirusTotal and various tabs like Security, Enviroment, Strings, Image etc.
* Click OK to continue

### Step 2: Explore handles

* In the Process Explorer, click View > select Lower Pane View > Handles to view the handles associated with the conhost.exe process.
* Question: Examine the handles. What are the handles pointing to?

![image](https://user-images.githubusercontent.com/33444140/236885402-61aca635-1a6f-4b49-9ddc-3863e913d89d.png)

* Handles pointing to the processes that are running now.

## Part 3: Exploring Windows Registry

The Windows Registry is a hierarchical database that stores most of the operating systems and desktop environment configuration settings.

* To access the Windows Registry, click Start > Search for regedit and select Registry Editor. Click Yes when asked to allow this app to make changes.

![image](https://user-images.githubusercontent.com/33444140/236886169-493da585-9ba8-4ef6-8eab-74b68b7928a3.png)

The Registry Editor has five hives. These hives are at the top level of the registry.
* HKEY_CLASSES_ROOT is actually the Classes subkey of HKEY_LOCAL_MACHINE\Software. It stores information used by registered applications like file extension association, as well as a programmatic identifier (ProgID), Class ID (CLSID), and Interface ID (IID) data.
* HKEY_CURRENT_USER contains the settings and configurations for the users who are currently logged in.
* HKEY_LOCAL_MACHINE stores configuration information specific to the local computer.
* HKEY_USERS contains the settings and configurations for all the users on the local computer. HKEY_CURRENT_USER is a subkey of HKEY_USERS.
* HKEY_CURRENT_CONFIG stores the hardware information that is used at bootup by the local computer.

* In a previous step, you had accepted the EULA for Process Explorer. Navigate to the EulaAccepted registry key for Process Explorer. Click to select Process Explorer in HKEY_CURRENT_USER > Software > Sysinternals > Process Explorer. Scroll down to locate the key EulaAccepted. Currently, the value for the registry key EulaAccepted is 0x00000001(1)

![image](https://user-images.githubusercontent.com/33444140/236886962-7cb94806-cf2b-45c9-b043-16467acb1544.png)

* Double-click EulaAccepted registry key. Currently the value data is set to 1. The value of 1 indicates that the EULA has been accepted by the user.

* Change the 1 to 0 for Value data. The value of 0 indicates that the EULA was not accepted. Click OK to continue.

![image](https://user-images.githubusercontent.com/33444140/236887262-dcc5bac4-0d24-4318-9321-c5b7348d975c.png)

What is value for this registry key in the Data column?

                The value changes to 0
* Open the Process Explorer. Navigate to the folder where you have downloaded SysInternals. Open the folder SysInternalsSuite > Open procexp.exe.

![image](https://user-images.githubusercontent.com/33444140/236887856-45ef5016-3181-4f3e-9f96-cf18905b1041.png)
