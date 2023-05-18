## Lab - Linux Servers

## Part 1: Servers

> Servers are essentially programs written to provide specific information upon request. Clients, which are also
programs, reach out to the server, place the request, and wait for the server response. Many different clientserver communication technologies can be used, with the most common being IP networks. This lab focuses
on IP network-based servers and clients

### Step 1: Access the command line.

* Log on to the CyberOps Workstation VM as the analyst, using the password cyberops. The account analyst is used as the example user account throughout this lab.
* To access the command line, click the terminal icon located in the Dock, at the bottom of VM screen. The terminal emulator opens.

### Step 2: Display the services currently running.

> Many different programs can be running on a given computer, especially a computer running a Linux
operating system. Many programs run in the background so users may not immediately detect what programs
are running on a given computer. In Linux, running programs are also called processes.

* Use the ps command to display all the programs running in the background:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/a8dd984e-b423-4287-8af6-1893904bc6e6)

* Why was it necessary to run ps as root (prefacing the command with sudo)?

    So that it will show the processess that are visible to or run through root user only.

* In Linux, programs can also call other programs. The `ps` command can also be used to display such process hierarchy. Use `–ejH` options to display the currently running process tree after starting the nginx webserver with elevated privileges.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/9da8eccc-9fcb-4e14-bf77-2ddac0c3ac55)

* As mentioned before, servers are essentially programs, often started by the system itself at boot time. The task performed by a server is called a service. In such fashion, a web server provides web services.
* The `netstat` command is a great tool to help identify the network servers running on a computer. The power of netstat lies on its ability to display network connections.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/0e044bfb-e2f1-44c4-899e-00d5c95cc1ed)

* As seen above, netstat returns lots of information when used without options. Many options can be used to filter and format the output of netstat, making it more useful.
*  Use `netstat` with the `–tunap` options to adjust the output of netstat. Notice that netstat allows multiple options to be grouped together under the same “-“ sign.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/7d10e6a2-93ff-48fc-b96d-5f1ec5c1d00b)

* What is the meaning of the –t, -u, –n, –a and –p options in netstat?

`-a` - --all
       Show both listening and non-listening sockets.  With the --interfaces option, show interfaces that are not up
       
`-t` - This option is used to display TCP (Transmission Control Protocol) connections.

`-u` - This option is used to display UDP (User Datagram Protocol) connections.

`-n` - This option instructs netstat to display numerical IP addresses and port numbers instead of attempting to resolve them to hostnames or service names.

`-p` - This option displays the program or process identifier (PID) associated with each network connection.

* Clients will connect to a port and, using the correct protocol, request information from a server. The netstat output above displays a number of services that are currently listening on specific ports. Interesting columns are:

* The first column shows the Layer 4 protocol in use (UDP or TCP, in this case).
* The third column uses the <ADDRESS:PORT> format to display the local IP address and port on which a specific server is reachable. The IP address 0.0.0.0 signifies that the server is currently listening on all IP addresses configured in the computer.
* The fourth column uses the same socket format <ADDRESS:PORT> to display the address and port of the device on the remote end of the connection. 0.0.0.0:* means that no remote device is currently utilizing the connection.
* The fifth column displays the state of the connection.
* The sixth column displays the process ID (PID) of the process responsible for the connection. It also displays a short name associated to the process.

* Sometimes it is useful to cross the information provided by netstat with ps. Based on the output of item (d), it is known that a process with PID 395 is bound to TCP port 80. Port 395 is used in this example. Use ps and grep to list all lines of the ps output that contain PID 395. Replace 395 with the PID number for your particular running instance of nginx:
