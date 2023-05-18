## Lab - Navigating the Linux Filesystem and Permission Settings

## Part 1: Exploring Filesystems in Linux

* The Linux filesystem is one of its most popular features. While Linux supports many different types of filesystems, this lab focuses on the ext family, one the most common filesystems found on Linux

### Step 1: Access the command line.

* Launch the CyberOps Workstation VM and open a terminal window.

### Step 2: Display the filesystems currently mounted.

> Filesystems must be mounted before they can be accessed and used. In computing, mounting a filesystem
means to make it accessible to the operating system. Mounting a filesystem is the process of linking the
physical partition on the block device (hard drive, SSD drive, pen drive, etc.) to a directory, through which the
entire filesystem can be accessed. Because the aforementioned directory becomes the root of the newly
mounted filesystem, it is also known as mounting point

* Use the lsblk command to display all block devices:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/98d57e5c-9b13-4ef2-9b91-b370116089fa)

* The output above shows that the CyberOps Workstation VM has three block devices installed: sr0, sda and sdb. The tree-like output also shows partitions under sda and sdb. Conventionally, /dev/sdX is used by Linux to represent hard drives, with the trailing number representing the partition number inside that device. Computers with multiple hard drives would likely display more /dev/sdX devices. If Linux was running on a computer with four hard drives for example, it would show them as /dev/sda, /dev/sdb, /dev/sdc and /dev/sdd, by default. The output implies that sda and sdb are hard drives, each one 
* Use the `mount` command to display more detailed information on the currently mounted filesystems in the CyberOps Workstation VM.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/485016b6-a206-4760-bb27-53900bdd697d)

* Run the mount command again, but this time, use the pipe | to send the output of mount to grep to filter the output and display only the root filesystem:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/623bb2bb-caab-4711-8ccc-982a07833a6e)

* In the filtered output above, mount shows us that the root filesystem is located in the first partition of the sda block device (/dev/sda1). We know this is the root filesystem because of the mounting point used: “/” (the slash symbol). The output also tells us the type of formatting used in the partition, ext4 in this case. The information in between parentheses relates to the partition mounting options.
* Issue the following two commands below on the `CyberOps Workstation VM`:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/cdca1fb7-18de-43a1-bead-bb903c73baf7)

### Step 3: Manually mounting and unmounting filesystems

> The mount command can also be used to mount and unmount filesystems. As seen in Step 1, the CyberOps
Workstation VM has two hard drives installed. The first one was recognized by the kernel as /dev/sda while
the second was recognized as /dev/sdb. Before a block device can be mounted, it must have a mounting
point.