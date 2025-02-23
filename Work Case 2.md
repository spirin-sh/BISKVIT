Опишіть набір базових дій в встановленому Вами гіпервізорі. (Микитенко Назарій)
- Створення нової віртуальної машини;
- Вибір/додавання доступного для віртуальної машини обладнання;
- Налаштування мережі та підключення до точок Wi-Fi;
- Можливість роботи з зовнішніми носіями (flash-пам’ять).


## Практична частина (Краснопір Богдан)

### Process of instalation

  As OS we chosed Kali Linux with GNOME GUI.

  1. Chose your location, language and keyboard configuration. (If your location is undefined, as in our case, you'll chose timezone)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890111842517002/2025-02-22_153849.png?ex=67bb4760&is=67b9f5e0&hm=4d40b77455b84e7e4d62dd583c360bcd286e4cfdf58719cb5988c8c9ff644310&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890111200792626/2025-02-22_153937.png?ex=67bb4760&is=67b9f5e0&hm=0c86f7d6489d9f080b0baaef04f4a7309f2c26f73dd601d4f61e5d5d2534aa24&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890110865244310/2025-02-22_153948.png?ex=67bb4760&is=67b9f5e0&hm=802627686a18a676d01357e58f30b8cef50ff6f26dc6c051c114411c64e79f2f&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890110596943952/2025-02-22_154023.png?ex=67bb4760&is=67b9f5e0&hm=d2581e89c880c7405be1ceb09df8faff1ef6e2872a6133ba95319d9415b4fd07&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890110261137500/2025-02-22_154050.png?ex=67bb475f&is=67b9f5df&hm=92fe344a76c6280c24a6b0eb6c8821717234415ab162f1e3ab84dc5ca35624dd&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890109930049641/2025-02-22_154110.png?ex=67bb475f&is=67b9f5df&hm=7989ce81397edd8a4b7a61033f1e0450358243eeaef6443a7c4e9f4cf5abaa25&)

  2. Configuring network. We are setting our hostname and proxy server (in our case we do it withou proxy)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890109514678426/2025-02-22_154156.png?ex=67bb475f&is=67b9f5df&hm=de843b01103e8ee3da402dab60eee5804369c4e17d5dfbfdce27374f25cf9214&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890109099577344/2025-02-22_154210.png?ex=67bb475f&is=67b9f5df&hm=480635879cae82176cf21425bc9a44f41540ebf256a4b98483dcd2b97f74ca7c&)

  3. Setting up users and passwords.

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890146223099924/2025-02-22_154320.png?ex=67bb4768&is=67b9f5e8&hm=24ef7b1d7384aa946c580e7117f4b1918140d9d72c84b8287fe0b9c9a082ee57&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890145984286751/2025-02-22_154359.png?ex=67bb4768&is=67b9f5e8&hm=6f3349d5d241ba5b89fba47c2f0acc0adf1368b7086b2bd88ed68fcdf760a8a4&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890145636155392/2025-02-22_154415.png?ex=67bb4768&is=67b9f5e8&hm=b683553bad90f503bff143dfeed43e6de2a09750776af07d8e8a430de9dbb95e&)

 4. Disks partition. We are using entire v-disk and installing all filen in one partition. Then finnishing partitioning. 

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890145275314176/2025-02-22_154515.png?ex=67bb4768&is=67b9f5e8&hm=c1af72d054e81c2f68e2f9d744c15b695e26ca2dcabdf397702b6963e7ebb379&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890144952483940/2025-02-22_154523.png?ex=67bb4768&is=67b9f5e8&hm=53e26e752fc9f451216ee25a477971a1c1c9596da8b1b0e1c1ea72358c354038&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890144663081001/2025-02-22_154540.png?ex=67bb4768&is=67b9f5e8&hm=2e4241cc9fca22500cc34d25529be827d5b9c3d9e765cebd13d6ea02beae4bf2&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890144277073991/2025-02-22_154612.png?ex=67bb4768&is=67b9f5e8&hm=46b435f12ec488341e13f0c5239a6e6167953971b302d3483b8df799b26ed993&)

  We use "Yes" option because we have completely empty disk. 

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890168901832856/2025-02-22_154630.png?ex=67bb476d&is=67b9f5ed&hm=ee8f5642049fd2eb0ad85984429635ad7c0147e18a29375cca090476f665818b&)

  5. Selecting software and installing GRUB.

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890168117493820/2025-02-22_154819.png?ex=67bb476d&is=67b9f5ed&hm=c69e2bf2f2eb2626e7a1685fbec6b6e4cd680a3acc4f7a1967330e776c86a19b&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890167832150118/2025-02-22_155723.png?ex=67bb476d&is=67b9f5ed&hm=7425f34e91636e622ea84d770ef6859abee80453a0ec46126df3666e89f77568&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890169442897941/2025-02-22_155729.png?ex=67bb476e&is=67b9f5ee&hm=e8afa8b7ec6568201fbe584810c4777cf3b92e7b109ba1a49d5db9eed438455f&)

  6. Instalation of system and Booting. 

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890168436129862/2025-02-22_154656.png?ex=67bb476d&is=67b9f5ed&hm=d39f5ab3b149f999bcd31ddda39a08d799043d8571c7d0446d0fc61184975cdf&)

![alt text](https://cdn.discordapp.com/attachments/853338697985687574/1342890169170133063/2025-02-22_155922.png?ex=67bb476e&is=67b9f5ee&hm=da6873dfa41674321345cfcd2562ceb9185a2866d62e181d7e97d7f984e3a2d7&)

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




