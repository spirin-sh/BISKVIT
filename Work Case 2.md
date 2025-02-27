## Опишіть набір базових дій в встановленому Вами гіпервізорі. (Микитенко Назарій)
### Створення нової віртуальної машини;
1. Click *"Create"* in the tool window.
2. Enter the name of the virtual machine.
3. Select the type and version of the OS to be installed. In our case, it is Linux with GNOME GUI.
4. Specify the amount of RAM that will be allocated for the virtual machine *(at least 2 GB is recommended)*. To make the virtual machine not too heavy, it is better to allocate 50% of the memory that is available on the main PC.
1. Specify the hard disk parameters and select the file type of the virtual disk of the machine. In *"Expert mode"* you can find more hard disk settings if necessary.
2. Select the storage format *(in our case it is "dynamic")*.
3. Click *"Create"*.

### Вибір/додавання доступного для віртуальної машини обладнання;
In the settings window, you can change the settings in the *"System"*, *"Media"*, *"Network"* and *"USB"* sections. For example, to add an optical drive, go to *"Media"*, click the add device icon, select 
*"Add optical drive"* and specify an ISO file or a physical drive. In the *"Network"* section, you can enable the adapter and select the connection type *(NAT or network bridge)*. After saving the changes, click *"OK"* and start the virtual machine.

### Налаштування мережі та підключення до точок Wi-Fi;
First, you need to open the virtual machine settings and go to the "Network" section, where you need to activate the adapter. In the "Connected to" field, you need to select the appropriate network mode. Most often, for simple access to the Internet, NAT mode is used, which allows the guest operating system to use the host connection without additional settings. In this case, in the "Name" field, you need to select the Wi-Fi adapter of the host computer *(for example, "Wi-Fi" or "wlan0")*. After saving the changes, first, to check the operability, start the virtual machine and check the Internet connection using the ping command in the command line terminal.

### Можливість роботи з зовнішніми носіями (flash-пам’ять);
First, download and install the latest version of the *VirtualBox Extension Pack*. This will add support for *USB 2.0* and *3.0*. 
Then you need to restart the system for the changes to take effect. After restarting VirtualBox, click *"Settings"* - *"USB"*. Enable the *USB 2.0 or 3.0* controller, add a new USB filter so that VirtualBox automatically connects the device to the virtual machine. In the *"Devices"* menu, select "USB" and click on the desired flash drive to connect it to the virtual machine.

## Практична частина (Краснопір Богдан)

### Process of instalation

  As OS we chosed Kali Linux with GNOME GUI.

  1. Chose your location, language and keyboard configuration. (If your location is undefined, as in our case, you'll chose timezone)

![alt text](https://i.imgur.com/a817m1l.png)

![alt text](https://i.imgur.com/lkuARgF.png)

![alt text](https://i.imgur.com/kK7jkiv.png)

![alt text](https://i.imgur.com/1XpRFjx.png)

![alt text](https://i.imgur.com/ho9fnzz.png)

![alt text](https://i.imgur.com/dQ5Jvf1.png)

![alt text](https://i.imgur.com/CYsKAnn.png)

  2. Configuring network. We are setting our hostname and proxy server (in our case we do it withou proxy)

![alt text](https://i.imgur.com/twdODA0.png)

![alt text](https://i.imgur.com/PauQ1bY.png)

  3. Setting up users and passwords.

![alt text](https://i.imgur.com/j0tkx2q.png)

![alt text](https://i.imgur.com/6MBgroy.png)

![alt text](https://i.imgur.com/1kmgh6x.png)

 4. Disks partition. We are using entire v-disk and installing all filen in one partition. Then finnishing partitioning. 

![alt text](https://i.imgur.com/im21xIt.png)

![alt text](https://i.imgur.com/YzxPmhE.png)

![alt text](https://i.imgur.com/lEkcInN.png)

![alt text](https://i.imgur.com/pGzc90U.png)

  We use "Yes" option because we have completely empty disk. 

![alt text](https://i.imgur.com/dlKSVfb.png)

  5. Selecting software and installing GRUB.

![alt text](https://i.imgur.com/ROswQ9e.png)

![alt text](https://i.imgur.com/5cO9Kzh.png)

![alt text](https://i.imgur.com/A7HTSEt.png)

  6. Instalation of system and Booting. 

![alt text](https://i.imgur.com/Wj9pRNT.png)

![alt text](https://i.imgur.com/mU8MMBJ.png)

>Після цього необхідно оновити пакети та систему для подальшого використання (`sudo apt upgrade` та `sudo apt update`)


## Порівняння Xfce з Gnome (Клімчук Ярослав)

### Загальні відомості

**Xfce** - is a lightweight desktop environment for UNIX-based operating systems. Xfce aims to be fast and light on system resources, while remaining visually appealing and easy to use.
- Initial Release: 1996  
- Key Principle: A classic desktop with panels, menus, and minimal effects  
- Architecture: Built on GTK+ (version 2, later 3, partially supports GTK4)  
- Default Look: Similar to Windows 95/XP, with a classic menu and taskbar  
- Components:  
  - xfwm – Built-in window manager  
  - Thunar – Lightweight file manager  
  - Xfce Panel – Customizable panel for menus, tray icons, and window switching  
  - Xfce Settings – Set of configuration utilities
     
**Gnome** - focuses on creating a completely free environment accessible to all users regardless of technical skill level, physical limitations, or language. Within GNOME, both native applications for end users are developed, as well as a set of tools for creating new applications that integrate tightly with the desktop environment.
- Initial Release: 1999  
- Key Principle: Minimalist design with a focus on simplicity and gesture-based interaction  
- Architecture: GTK4, full Wayland support  
- Default Look: No traditional menu, replaced by "Activities Overview"  
- Components:  
  - Mutter – Window manager  
  - Nautilus – File manager  
  - GNOME Shell – Main shell with gesture navigation  
  - GNOME Control Center – Centralized settings panel

### Основні відмінності

| Feature            | Xfce                        | GNOME                      |
|--------------------|----------------------------|----------------------------|
| **Resource Usage** | 200-500MB RAM, low CPU load | 600+MB RAM, higher CPU usage |
| **Speed**         | Fast, works well on older PCs | Moderate, requires modern hardware |
| **Simplicity**    | Classic, familiar interface | Minimalist, takes time to adapt |
| **Customization** | High, can tweak panels, buttons | Lower, requires extensions |
| **Functionality** | Basic but extendable | Wide application ecosystem |
| **Wayland Support** | No support | Full support |
| **Stability**     | Very stable, rare breaking updates | Some changes may break compatibility |
| **Best For**      | Older PCs, users who prefer a classic style | New devices, users who prefer modern aesthetics |

## Плюси та мінуси

### Xfce
**Pros:**
Lightweight, fast, perfect for low-end machines  
Classic, convenient interface without unnecessary effects  
Flexible customization of panels, menus, and hotkeys  

**Cons:**
Fewer visual effects, outdated look  
Slow development cycle, rare updates  
No Wayland suppor

### GNOME
**Pros:**
Modern, minimalist design  
Supports gestures, Wayland, and new technologies  
Rich ecosystem of integrated applications    

**Cons:**
High resource usage  
Limited out-of-the-box customization without extensions  

## Owerall
If you need **a highly customizable, lightweight environment** → **Xfce**  
If you want **a modern desktop with strong technological integration** → **GNOME**  




