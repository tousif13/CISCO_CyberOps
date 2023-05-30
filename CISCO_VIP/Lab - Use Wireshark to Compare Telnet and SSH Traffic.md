## Lab - Use Wireshark to Compare Telnet and SSH Traffic

> Wireshark is a network protocol analyzer that lets you see what’s happening on your network at a microscopic
level. You can capture packets and store them for offline analysis. Wireshark includes many tools for deep
inspection of hundreds of network protocols. In this lab, you will use Wireshark to capture and inspect web
traffic, Telnet traffic, and SSH traffic.

### Step 1: Open a terminal window in the CSE-LABVM.

* Launch the CSE-LABVM.
* Double-click the Terminal icon to open a terminal.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/08117523-6b04-4c88-9ea5-bd93f99077ed)

### Step 2: Explore the Wireshark protocol analyzer.

* To capture traffic on your VM, you need to run Wireshark in promiscuous mode, which requires running with escalated privileges using sudo. Enter the sudo wireshark command, and then enter password for the password. The Wireshark graphical user interface (GUI) will open up.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/e7dafbc1-ea53-4efe-98a7-dc84fbb4c2e9)

* Under the listing of interfaces, select any, and then click Capture > Start from the menus. Alternatively, you can click the shark fin icon. Wireshark will begin capturing packets. 
* If you already have Firefox open, you may see traffic captured in the Wireshark interface. If Firefox is not open, go ahead and open it now. In Wireshark, you should now see captured TCP traffic in the top third of the window.
* In Firefox, enter www.cisco.com to visit the Cisco website. After the website loads, you can close Firefox
* Return to Wireshark and click Capture > Stop from the menus. Alternatively, you can click the red square button next to the shark fin.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/0f9b9e29-5828-4e01-be3e-f95e7e167af3)

* In Wireshark, you will see the filter field and three key panes or work areas:
* `The Apply a display filter` field is directly below the toolbar.
* `The Packet List pane` includes the following columns for each captured packet:
* `No` - the number of the packet (in numerical order).
* `Time` - the timestamp of the packet
* `Source` - the source IP address of the packet
* `Destination` - the destination IP address of the packet
* `Protocol` - the protocol of the packet
* `Length` - the number of bytes captured for this packet
* `Info` - additional information about the packet’s content

* The Packet Details pane shows the protocols and protocol fields of the selected packet. Notice that the fields can be expanded or collapsed by clicking the arrow next to the field.
* The Packet Bytes pane shows the byte details of the selected packet. As you select parts of the packet in the Packet Details pane, the corresponding bytes will be highlighted in the Packet Bytes pane. The left side shows the hexadecimal representation of the bytes, and the right side shows the ASCII representation.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/b892c25d-ba50-46b1-bfa9-aeed6432f25d)

### Step 3: Capture and analyze unencrypted Telnet traffic.

* Start a new capture. In the Unsaved packets… dialog box, click Continue without Saving. This will clear out the packets from your last capture and start a new capture.
* Double-click the Terminal icon to open a new terminal window. 
* You can simulate a remote login to your VM by entering the telnet localhost command, and then logging in as cisco with password as the password.
* Enter the exit command to end the Telnet session:
* Return to Wireshark and stop the capture.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/769618c1-14da-4c09-aafe-9adf5463a602)

* In the Apply a display filter field, type telnet and press Enter to filter for only Telnet packets.
* On the toolbar, click the magnifying glass icon to Find a packet. Additional search features are now shown below the Apply a display filter field
* Click the arrows next to Display filter and change it to String. Then click the arrows next to Packet list and change it to Packet details. 
* To find the packet requesting login information, type labvm login: in the field next to String, and then press Enter or click Find. Wireshark will highlight the packet that contains the "labvm login:" text string.
* In the Packet Details pane, click the arrow next to Telnet to expand its content. You should see that labvm login: is the data for this packet. The data for the packet is also shown in Packet Bytes pane. You can tell that the text was sent unencrypted because you can read it.
* In the Packet List pane, click the highlighted packet with labvm login as the data to select it

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/32e7da01-071e-453f-b9d2-d10f740df74a)

* To find the username and password, use your down arrow on the keyboard to select the next packet. In the Packet Details pane, you should see the value for Data under Telnet is the first letter you typed in the field for "labvm login:" prompt, which was c for cisco. If you click the down arrow again, you will see the next packet's data is also c. This is because the packet is listed twice: one time for source sending to destination and again for destination receiving the packet. Because the source and destination are the same interface (loopback 127.0.0.1), the packet is listed twice by Wireshark.
* Continue to press the down arrow key until you reach the last packet with a data value of o for the username cisco
* Continue to click the down arrow until you will see Password: in the Data field. Continue pressing the down arrow to read the data of the next eight packets which reveal, one letter at a time, that password is the password for user cisco.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/777e11ee-3207-417a-8824-88c777d699b5)

* If you continue to press the down arrow through the rest of the captured packets, you will see all the text sent and received during the Telnet session, including your exit command and the logout message. 

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/8227ceca-b453-44d9-b815-2114104fd818)

### Step 4: Capture and analyze encrypted SSH traffic

* Start a new capture. In the Unsaved packets… dialog box, click Continue without Saving. This will clear out the packets from your last capture and start a new capture.
* Return to your open terminal window or start a new terminal session.
* To simulate an SSH login, enter the command ssh localhost. If this is your first time to use the command, the system warns you about the authenticity of localhost and asks you if you want to continue. Enter yes, and then password as the password to log in

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/a228e27d-f899-4890-946a-3f40077935e9)

* Return to Wireshark and stop the capture. If you left telnet as the search term in the Apply a display filter field, no packets will be listed. Change the search term from telnet to ssh. All the packets from your SSH session should now be shown in the Packet List pane.
* In the Packet Details pane, expand the SSH Protocol fields to view the content. In the Packet List pane, click the first packet, and then use the down arrow to view a variety of the SSH packets. Notice that the Data for the SSH Protocol field shows that all the data is encrypted.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/0cd60f36-8978-4213-b3f5-2330478c2801)
