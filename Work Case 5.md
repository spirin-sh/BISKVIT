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
