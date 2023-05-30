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

