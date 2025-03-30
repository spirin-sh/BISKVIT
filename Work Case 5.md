## 1.1. В чому різниця при роботі з периферією у ОС Linux та ОС Windows? (Микитенко Назарій)

## 1.2. В чому суть операції монтування, для чого вона використовується та як? (Краснопір Богдан)

Mounting is a conection process between drive device and operating system. If drive is not mounted you won't be able to do anything with it. So to make disk work you'll need to mount it.

In Windows mounting is being done automaticaly, unlike Linux. On some Linux distros you'll need to do it by yourself.

To mount a drive you need to chose or create a new directory, where point of mounting will be. We can imagine Linux directories like a tree - our new mounting point will be new branch or the tree. 

> You can't mount drive on non-existent directory

You can mount disk by 2 ways: by terminal command or disk mannager

### Terminal

To mount by terminal we need to know our new disk name. To get disk name, use `lsblk -lf`. This command will show you some information about used disks, their names, file system, their mount directories. We need the NAME and MOUNTPOINT collums. If you see drive with name like _sda4_ without mountpoint - thats it (not count sda and sda1). 

After we know drive name, create new directory or use existing that you like. Now use `sudo mount /dev/<disk name> /<directory of mountpoint>`. It'll look like this: `mount /dev/sda4 /media/mydrive1`

To mount it permamently, use `/dev/sdc1 /<mountpoint> <disk name> default 0 0`.

### Disk mannager

To make process easier, you can use disk mannager if it supported in your disto. I'll show you how to do it on Ubuntu:

Firstly, you need to find your drive on disk mannager: 

![image](https://github.com/user-attachments/assets/0df95a12-74e3-4a21-af3c-377a83f4af3e)

Then press "Play" button and it'll start mounting your drive.

![image](https://github.com/user-attachments/assets/1b04a1c9-f067-4448-a708-ca05938d404d)

To mount it permamently, you need to open "Edit Mount Options..." and tick near "Mount at system startup" option. Also, you can edit your mounting preferences here. 



## Methodology for Connecting USB and Printer to Linux VM, Copying and Printing Files (Клімчук Ярослав)





### 1. Connecting the USB Flash Drive
To connect the USB flash drive to the virtual machine:

1. Ensure the USB flash drive is physically connected to the host machine.
2. In the virtualization software menu, navigate to **"Devices" > "USB"**.
3. Select the USB flash drive from the list to attach it to the VM.
4. The USB should automatically mount in Linux, typically under `/media/<username>/<flash_drive_name>`.

### 2. Copying a File via Graphical Interface
To copy a file from the USB flash drive to the virtual machine using the graphical interface:

1. Open the file manager .
2. Navigate to the USB mount point (e.g., `/media/<username>/<flash_drive_name>`).
3. Locate the file you wish to copy, select it, and press **Ctrl+C** to copy.
4. Navigate to the desired directory on the VM .
5. Press **Ctrl+V** to paste the file into the directory.

### 3. Connecting the Printer
To connect the printer to the virtual machine:

1. Ensure the printer is connected to the host machine and powered on.
2. In the virtualization software menu, go to **"Devices" > "USB"**.
3. Select the printer from the list to attach it to the VM.
4. In the Linux VM, open the printer settings. This may vary by desktop environment; for example, in Ubuntu, go to **"Settings" > "Printers"**.
5. If the printer does not appear automatically, click **"Add Printer"** and follow the on-screen instructions to select the printer model and install any required drivers.

### 4. Printing a File via Graphical Interface
To print the copied file using the graphical interface:

1. Open the copied file in an appropriate application (e.g., a text editor for a text file).
2. Select **"File" > "Print"** from the menu.
3. In the print dialog, select the connected printer.
4. Adjust any print settings as needed (e.g., number of copies, page range).
5. Click **"Print"** to send the file to the printer.

### 5. Copying and Printing Another File via Terminal
To copy another file from the USB flash drive to the virtual machine and print it using the terminal:

1. Copy another file to the desired directory:
cp <another_filename> /home/<username>/Documents/
2. Navigate to the directory where the file was copied:
cd /home/<username>/Documents/
3. Print the file using the lp command:
lp <another_filename>
