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

* Sometimes it is useful to cross the information provided by `netstat` with `ps`. Based on the output of item (d), it is known that a process with `PID 395` is bound to `TCP port 80`. Port 395 is used in this example. Use ps and grep to list all lines of the ps output that contain PID 395. Replace 395 with the PID number for your particular running instance of nginx:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/94cd8f41-c311-48bc-b0c0-181ce60f4994)

* In the output above, the ps command is piped through the grep command to filter for only the lines containing the number 395. The result is three lines with text wrapping.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/677c8dce-44df-4bda-81ae-4b4cb3d7571b)

* The process PID 542 is nginx. How could that be concluded from the output above?
* What is nginx? What is its function?

> Nginx (pronounced "engine-x") is a popular open-source web server and reverse proxy server. Originally developed to address the C10k problem (handling 10,000 concurrent connections), Nginx has gained widespread adoption due to its high performance, scalability, and versatility. Some of its functions are Web Server, Reverse Proxy Server, Load Balancer, Caching, SSL/TLS Termination, HTTP/2 and WebSocket Support, Reverse Proxy for Microservices etc.

## Part 2: Using Telnet to Test TCP Services

> Telnet is a simple remote shell application. Telnet is considered insecure because it does not provide
encryption. Administrators who choose to use Telnet to remotely manage network devices and servers will
expose login credentials to that server, as Telnet will transmit session data in clear text. While Telnet is not
recommended as a remote shell application, it can be very useful for quickly testing or gathering information
about TCP services.

> The Telnet protocol operates on port 23 using TCP by default. The telnet client however, allows for a different
port to be specified. By changing the port and connecting to a server, the telnet client allows for a network
analyst to quickly assess the nature of a specific server by communicating directly to it.

* In Part 1, nginx was found to be running and assigned to port 80 TCP. Although a quick internet search revealed that nginx is a lightweight web server, how would an analyst be sure of that? What if an attacker changed the name of a malware program to nginx, just to make it look like the popular webserver? Use telnet to connect to the local host on port 80 TCP:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/1a7be128-065b-49c0-ae0b-9169a7264346)

* Press a few letters on the keyboard. Any key will work. After a few keys are pressed, press ENTER. Below is the full output, including the Telnet connection establishment and the random keys pressed (12345, this case):

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/aca42fae-7b3b-4723-9803-6fa0fdc0e928)

> Thanks to the Telnet protocol, a clear text TCP connection was established, by the Telnet client, directly
to the nginx server, listening on 127.0.0.1 port 80 TCP. This connection allows us to send data directly to
the server. Because nginx is a web server, it does not understand the sequence of random letters sent to
it and returns an error in the format of a web page.

* Looking at the netstat output presented earlier, it is possible to see a process attached to `port 22`. Use `Telnet` to connect to it.
* Port 22 TCP is assigned to SSH service. SSH allows an administrator to connect to a remote computer securely.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/b529cc90-ebde-4b55-ab15-1b6956ba396d)

* Use Telnet to connect to port 68. What happens? Explain.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/cd368168-a816-4555-bd80-173c92b8354e)

* Port 68 is actually used by the Bootstrap Protocol (BOOTP) server, not the client. Telnet, on the other hand, is a protocol used for remote terminal access and does not use port 68 or BOOTP. Telnet traditionally uses port 23 for communication. It establishes a connection to a remote host's Telnet server on port 23, allowing interactive access to that system's command line.

## Reflection Questions

* What are the advantages of using netstat?

        Netstat provides real-time insights into network connections, open ports, and network statistics, allowing you to monitor network activity, troubleshoot connectivity issues, identify unauthorized connections, and analyze network performance. With its ability to display connection details, port statuses, associated processes, and protocol-specific information, netstat empowers administrators to effectively manage and secure their network infrastructure across different platforms.
        
* What are the advantages of using Telnet? Is it safe?

        Telnet allows remote access to a device's command-line interface, providing advantages such as easy remote management, troubleshooting, and configuration of network devices. However, Telnet is considered insecure because it transmits data, including passwords, in plaintext, making it vulnerable to eavesdropping and unauthorized access. It is recommended to use more secure alternatives like SSH (Secure Shell) for remote access to ensure the confidentiality and integrity of transmitted data.
