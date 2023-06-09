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

* Use the ls -l command to verify that the directory second_drive is in the analyst's home directory.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/e27b737b-7849-47aa-ab66-a9fe6cd36fc9)

* If the directory second_drive does not exist, use the `mkdir second_drive` command to create it.
* Use `ls -l` again to list the contents of the newly created second_drive directory.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/46f93355-94a8-464c-87c7-880d0153413c)

* The directory is empty
* Use the mount command to mount `/dev/sdb1` on the newly created `second_drive` directory. The syntax of mount is: mount [options] <device to be mounted> <mounting point>

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/7f2c7b55-6408-4334-bc4a-8ddd49dd8d23)

* No output is provided means the mounting process was successful
* Now that the `/dev/sdb1` has been mounted on `/home/analyst/second_drive`, use `ls -l` to list the contents of the directory again.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/8d9224c4-e361-4fc9-b676-ac6c8e78a4a8)

* The directory is longer empty as we mounted files from `/dev/sdb1`
*  Issue the mount command with no options again to display detailed information about the /dev/sdb1 partition. As before, use the grep command to display only the /dev/sdX filesystems:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/53e795ec-f3bf-4f4c-b5b2-f789edf67f39)

* Unmounting filesystems is just as simple. Make sure you change the directory to something outside of the mounting point and use the umount command, as shown below:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/fe85972f-bf45-4896-80d0-c4d04ca00d85)

## Part 2: File Permissions

> Linux filesystems have built-in features to control the ability of the users to view, change, navigate, and
execute the contents of the filesystem. Essentially, each file in filesystems carries its own set of permissions,
always carrying a set of definitions about what users and groups can do with the file.

### Step 1: Visualize and Change the File Permissions.

* Navigate to /home/analyst/lab.support.files/scripts/
* Use the ls -l command to display file permissions.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/ca3aac7a-ff68-4ccd-a8fc-6c756fb4abf0)
  
* The permissions for cyops.mn are –rw-r--r--. What does that mean?
  
      That it has read and write permissions for user and only read permission for group and world users.
* The touch command is very simple and useful. It allows for the quick creation of an empty text file. Use the command below to create an empty file in the /mnt directory:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/be65e1b2-baef-4b4c-a930-cb3b71c71013)

* Why was the file not created? List the permissions, ownership and content of the /mnt directory and explain what happened. With the addition of -d option, it lists the permission of the parent directory. Record the answer in the lines below.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/fe477a62-0330-460d-8e46-172af5df363c)

* What can be done for the touch command shown above to be successful?
  
        Giving the directory write permission will be done for the touch command.
  
* The chmod command is used to change the permissions of a file or directory. As before, mount the /dev/sdb1 partition on the /home/analyst/second_drive directory created earlier in this lab
* Change to the second_drive directory and list the contents of it:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/9afa2ed2-f031-487b-a9db-17105b4f2b3f)

* Use the `chmod` command to change the permissions of `myFile.txt`
  
![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/55ce9990-bd82-4d99-a982-bb1f35b38da9)

* The chmod command takes permissions in the octal format. In that way, a breakdown of the 665 is as follows:
  
  6 in octal is 110 in binary. Assuming each position of the permissions of a file can be 1 or 0, 110 means rw- (read=1, write=1 and execute=0).

  Therefore, the `chmod 665 myFile.txt` command changes the permissions to:

  `Owner`: rw- (6 in octal or 110 in binary)

  `Group`: rw- (6 in octal or 110 in binary)

  `Other`: r-x (5 in octal or 101 in binary)
  
* What command would change the permissions of myFile.txt to rwxrwxrwx, granting any user in the
system full access to the file?

        chmod 777 myFile.txt
* The `chown` command is used to change ownership of a file or directory. Issue the command below to make root the owner of the myFile.txt:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/58cdbe4a-d43a-48e8-8a64-5b326a7f18b7)

### Step 2: Directory and Permissions

> Similar to regular files, directories also carry permissions. Both files and directories have 9 bits for the
permissions of the owner/user, the group, and others. There are also three more bits for special permissions:
setuid, setgid, and sticky which is beyond the scope of this lab.

* Change back to the `/home/analyst/lab.support.files` directory and issue the `ls -l` command to list all the files with details:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/b81533fc-9eb4-473c-a775-e2d89aa5885f)

* Compare the permissions of the malware directory with the mininet_services file. What is the difference between beginning part of the malware line and the mininet_services line?

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/90e81a43-b439-425c-b908-259ee4a78059)

> The letter ‘d’ at the beginning of the line indicates that the file type is a directory and not a file. Another
difference between file and directory permissions is the execution bit. If a file has its execution bit turned
on, it means it can be executed by the system. Directories are different than files with the execution bit set
(a file with the execution bit set is an executable script or program). A directory with the execution bit set
specifies whether a user can enter that directory
  
## Part 3: Symbolic Links and other Special File Types

### Step 1: Examine file types
  
* Use the ls -l command to display the files in the /home/analyst folder. Notice the first characters of each line are either a “–“ indicating a file or a “d” indicating a directory.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/81db3a39-a9cc-45cd-8cb4-f109ab285e22)

* Produce a listing of the /dev directory. Scroll to the middle of the output and notice how the block files begin with a “b”, the character device files begin with a “c” and the symbolic link files begin with an “l”:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/c234c2be-4ce0-4391-bec5-7c7678f2d1df)

* Symbolic links in Linux are like shortcuts in Windows. There are two types of links in Linux: symbolic links and hard links. The difference between symbolic links and a hard links is that a symbolic link file points to the filename of another file and a hard link file points to the contents of another file. Create two files by using echo:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/d7c80b8c-1fc0-4db9-a09d-8ab2960956a7)

* Use `ln –s` to create a symbolic link to `file1.txt`, and `ln` to create a hard link to `file2.txt`:
* Use the ls –l command and examine the directory listing:

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/10efe0fb-bd2b-473b-85e4-04fcc73afe01)

> Notice how the file file1symbolic is a symbolic link with an l at the beginning of the line and a pointer ->
to file1.txt. The file2hard appears to be a regular file, because in fact it is a regular file that happens to
point to the same inode on the hard disk drive as file2.txt. In other words, file2hard points to the same
attributes and disk block location as file2.txt. The number 2 in the fifth column of the listing for file2hard
and file2.txt indicates that there are 2 files hard linked to the same inode. For a directory listing the fifth
column indicates the number of directories within the directory including hidden folders.
  
* Change the names of the original files: file1.txt and file2.txt, and notice how it effects the linked files
  
![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/d0600610-0ff3-4dc9-b183-809fa3dc92c0)

* Notice how file1symbolic is now a broken symbolic link because the name of the file that it pointed to file1.txt has changed, but the hard link file file2hard still works correctly because it points to the inode of file2.txt and not its name, which is now file2new.txt.

