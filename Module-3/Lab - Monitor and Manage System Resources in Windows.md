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
