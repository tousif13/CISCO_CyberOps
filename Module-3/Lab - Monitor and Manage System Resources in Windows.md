# Lab - Monitor and Manage System Resources in Windows

## Part 1: Starting and Stopping the Routing and Remote Access service

You will explore what happens when a service is stopped and then started. In this part, you will use routing
and remote access service as the example service. This service allows the local device to become a router or
a remote access server

* Navigate to the Control Panel > Click Network and Sharing Center
* Click Change adapter settings in the left pane. Reduce the size of the Network Connections window and leave it open.
* Navigate to the Administrative Tools. (Navigate to the Control Panel > Click Administrative Tools)
* In the Administrative Tools window, double-click the Performance Monitor icon.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/ecbcc7de-8f6f-47c2-8aa6-7cd76a1e6cbc)

* In the Performance Monitor window, make sure Performance Monitor under Monitoring Tool heading in the left pane is highlighted. Click the Freeze Display icon (pause button) to stop the recording.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/386d2adc-e87b-44ad-80f2-f3596aa74a23)

* Navigate to the Administrative Tools and select Services
* Expand the width of the Services window so you have a clear view of the content. Scroll down in the right pane until you see the service Routing and Remote Access. Double-click Routing and Remote Access.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/943de9d8-371d-4837-b2da-071a3c4e0161)

* In the Routing and Remote Access Properties (Local Computer) window opens. In the Startup type drop-down field, select Manual and then click Apply

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/16f6c98e-cc7c-4e08-baea-6b99564aa6a0)

* Navigate to Performance Monitor window. Click the Unfreeze Display icon to start the recording. 
* Click the Routing and Remote Access Properties (Local Computer) window. To start the service, click
Start. A window with a progress bar opens.
* The Routing and Remote Access Properties (Local Computer) window now shows the Stop and Pause button active. Leave this window open.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/54fc371a-fa7d-4e81-9057-bd6527032bb1)

* Navigate to Network Connections window. Press the function key F5 to refresh the content.
* Navigate to Routing and Remote Access Properties (Local Computer) window and click Stop. Note: If Stop is greyed out, click Apply and change the service status.
* Navigate to Network Connections window.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/b30421a9-bd28-45e7-88f8-587c6db6ee97)

* Click the Change graph type drop-down menu, select Report.
* The display changes to report view.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/88db409c-3cba-4a7f-8eef-af9f5111f98a)

* Click the Routing and Remote Access Properties (Local Computer) window. In the Startup type field, select Disabled and click OK.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/c1d56280-36ac-45bf-8c74-244b5f9a7959)

* Click the Services window.
* What is the Status and Startup Type for Routing and Remote Access?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/63151cda-331b-45bf-9d1d-af1b8308b0c0)

* Click the Performance Monitor window. Click the Unfreeze Display icon to start the recording
* Close all open windows you opened during Step 1 of this lab.

## Part 2: Working in the Computer Management Utility

The Computer Management is used to manage a local or remote computer. The tools in this utility are grouped into three categories: system tools, storage, and services and applications.

* Click Control Panel > Administrative Tools. Select Computer Management. 
* In the Computer Management window, expand the three categories by clicking on the arrow next to System Tools.
* Click the arrow next to Event Viewer then click the arrow next to Windows Logs. Select System.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/f30a0a30-ebeb-4692-ac35-42f6a2340b0a)

* The Event Properties window opens for the first event. Click the down arrow key to locate an event for Routing and Remote Access. You should find four events that describe the order for starting and stopping the Routing and Remote Access service.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/d50bdd66-6d72-40d5-ad0d-ae66e70e1538)

* Close all open windows.

## Part 3: Configuring Administrative Tools

For the rest of this lab, you will configure Advanced Administrative Tool features and monitor how this affects
the computer.

* Click Control Panel > Administrative Tools > Performance Monitor. The Performance Monitor window opens. Expand Data Collector Sets. Right-click User Defined, and select New > Data Collector Set
* The Create new Data Collector Set window opens. In the Name field, type Memory Logs. Select the Create manually (Advanced) radio button, and click Next.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/ac5eeaae-e134-411e-acc2-e5d80a06338b)

* In the What type of data do you want to include? window, check the Performance counter box then click Next.
* In the Which performance counters would you like to log? window, click Add.
* From the list of available counters, locate and expand Memory. Select Available MBytes and click Add>>

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/492a50df-343e-450e-8012-b55764cfa00a)

* Set the Sample interval field to 4 seconds. Click Next

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/65c18e3d-a6b6-44d4-858d-7a3d072c46b6)

* In the Where would you like the data to be saved? screen, click Browse.
* In the Browse For Folder window , select your (C:) drive which is Local Disk (C:). Select PerfLogs and click OK.
* The Where would you like the data to be saved? window opens with the directory information that you selected in the previous step. Click Next.
* In the Create the data collector set? screen, click Finish.
* Expand User Defined and select Memory Logs. Right-click Data Collector01and select Properties.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/98db0528-377a-4da5-a2b9-d890cfc56c72)

* In the DataCollector01 Properties window, chhange the Log format: field to Comma Separated.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/b543ab93-764e-4af7-949e-b5bae1e26ae4)

* Click the File tab.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/42244fc5-6b60-401d-88e6-25b4f874b351)

* Click OK.

* Select the Memory Logs icon in the left pane of the Performance Monitor window. Click the green arrow icon to start the data collection set. Notice a green arrow is placed on top of the Memory Logs icon.
* Click the black square icon to stop the data collection set.
* Click Start > Computer,and click drive C: > PerfLogs. Locate the folder that starts with your PC’s name followed by a timestamp, DESKTOP-NDFE14H_20170514-000001 in the example. Double-click the folder to open it, and then double-click the DataCollector01.csv file. If prompted, click Continue to permit access to the folder.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/2777415c-88e0-41c1-b7f6-91b2cfbad79a)

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/8d2f296b-11e8-49fe-ac90-a234a000de48)

* Close the csv file and the window with the PerfLogs folder.
* Select the Performance Monitor window. Right-click Memory Logs > Delete.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/7dd78c4d-185b-4baf-9321-02fed9c7c49a)
