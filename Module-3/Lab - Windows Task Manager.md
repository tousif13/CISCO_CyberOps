# Lab - Windows Task Manager

## Part 1: Working in the Processes tab

* Open a command prompt and a web browser.
* Microsoft Edge is used in this lab; however, any web browser will work. Just substitute your browser name whenever you see Microsoft Edge.
* Right-click the Task bar to open Task Manager. Another way to open the Task Manager is to press CtrlAlt-Delete to access the Windows Security screen and select Task Manager.
* Click More details to see all the processes that are listed in the Processes tab.
* Expand the Windows Command Processor heading.

![image](https://user-images.githubusercontent.com/33444140/237063689-69510259-0bab-46b3-b18a-0753349ff3cd.png)

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/741542c5-9d11-4ab1-8911-3687555a6b2e)

* There are three categories of processes listed in the Processes tab: Apps, Background processes, and Windows processes.
* The Apps are the applications that you have opened, such as Microsoft Edge, Task Manager, and Windows Command Processor, as shown in the figure above. Other applications that are opened by
the users, such as web browsers and email clients, will also be listed here.
* The Background processes are executed in the background by applications that are currently open.
* The Windows processes are not shown in the figure. Scroll down to view them on your Windows PC. Windows processes are Microsoft Windows services that run in the background.
* Some of the background processes or Windows processes may be associated with foreground processes. For example, if you open a command prompt window, the Console Window Host process will be started in the Windows process section, as shown below.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/ac0ec366-736e-449a-ada3-3e311e3f2cf3)

* Right-click Console Window Host and select Properties.
* Question: What is the location of this filename and location of this process?
          C:\Windows\System32
 
![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/559d2bdc-a970-4a80-81ef-a6e3936d362d)

* Close the command prompt window.
* Click the Memory heading. Click the Memory heading a second time.
* What effect does this have on the columns?
          It shows Memory usage in Descending order and Ascending order.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/50b47118-edbc-4a6e-b4ca-bf52b9cf787a)

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/4280858f-549f-424f-90d7-923bcb4c0dcb)

* Right-click on the Memory heading, and then select Resource values > Memory > Percents.
* What affect does this have on the Memory column?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/4d5d30d3-8c53-4c49-be4f-e208165969ba)

This could be useful to see how much percentage of memory is the process using

* In the Task Manager, click the Name heading.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/7e7ba401-c0d7-46a2-8d4c-80bc31ab0efa)

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/de0b6d54-cd5b-4647-b549-3d0ef92cb83b)

          It shows Name in Alphabetical order.

* Double-click the Microsoft Edge.
* Question: What happens?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/06996c3b-9864-4ae1-995f-ccbd175d8105)

* Return to the Task Manager and right-click Microsoft Edge. Select End task.
* Question: What happens to the web browser windows?

          Microsoft Edge gets closed.

## Part 2: Working in the Services tab

* In the Task Manager window, click the Services tab. Use the scroll bar on the right side of the Services window to view all the services listed.
* What statuses are listed?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/ab585f52-09d4-4b7a-8629-6c5cddbb7d43)

## Part 3: Working in the Performance tab

* In the Task Manager window, click the Performance tab. 

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/22e2fd39-d256-474f-968f-12e15fd584ea)

          9 threads are running

* Click the Memory in the left panel of the Performance tab.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/e98de992-5510-4b75-ba8f-39d477a3f969)

          Total 8 GB physical memory
          Total 1.5 GB Available physical memory
          Total 6.3 physical memory is being used by the computer
          
* Click the Ethernet Chart in the left panel of the Performance tab.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/f0c09699-01c2-4e03-b5d1-8449e94d2b55)

          As the ethernet is not active. It's not showing any data

* Click Open Resource Monitor to open the Resource Monitor utility from the Performance tab in Task Manager

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/623adff8-b280-4e2e-b087-6c6811931e46)

* Why is it important for an administrator to understand how to work within the Task Manager?

>  It is important for an administrator to understand the work within the Task Manager. The Task Manager provides real-time information about the system's performance, including CPU, memory, disk, and network usage. It also provides information about the application's resource consumption, which can help administrators identify potential issues and conflicts. It allows administrators to identify resource-heavy startup items and optimize the boot process, improving overall system performance and reducing startup time. It is particularly useful for managing remote desktop sessions or resolving user-related issues.
