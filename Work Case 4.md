## 1.Робота з менеджерами пакетів

### 1.1 Дайте розгорнуте визначення таким поняттям як «пакет» та «репозиторій».

#### What is a **Package**?
A **Package** is an archive that contains the necessary files to install and run a piece of software on a Linux system. It typically includes:
- Executable files or binaries
- Libraries required for the program
- Configuration files
- Metadata describing dependencies and versioning
- Scripts to automate installation and removal processes

Common package formats:
- **.deb** — for Debian-based distributions (Ubuntu, Linux Mint)
- **.rpm** — for Red Hat-based distributions (Fedora, CentOS, openSUSE)
- **.tar.gz**, **.tar.xz** — compressed archives, often used for source code distribution.

#### What is a **Repository**?
A **Repository** is a centralized storage location where software packages are kept and maintained. Repositories are used by package managers to retrieve and install software.

Repositories can be:
- **Official** — provided and maintained by the distribution maintainers.
- **Third-party** — provided by external developers or communities.

A repository contains:
- Packages (applications, libraries, updates)
- Metadata (version info, dependencies, digital signatures)
- Security patches and bug fixes


### 1.2 Надайте короткий огляд існуючих менеджерів пакетів у Linux. Охарактеризуйте їх основні можливості.
A **Package Manager** is a tool that automates the process of installing, updating, configuring, and removing software packages on a Linux system.

---

#### APT (Advanced Package Tool)
- **Distributions**: Debian, Ubuntu, Linux Mint, and derivatives
- **Package Format**: `.deb`
- **Common Commands**:
  - `sudo apt update` — refresh package lists
  - `sudo apt install <package>` — install a package
  - `sudo apt upgrade` — upgrade all packages
  - `sudo apt remove <package>` — remove a package
- **Key Features**:
  - Simple and user-friendly
  - Handles dependencies automatically
  - Supports multiple repositories
  - Integration with PPAs (Personal Package Archives)

---

#### DNF (Dandified YUM)
- **Distributions**: Fedora, Red Hat Enterprise Linux (RHEL), CentOS (from version 8)
- **Package Format**: `.rpm`
- **Common Commands**:
  - `sudo dnf check-update` — check for available updates
  - `sudo dnf install <package>` — install a package
  - `sudo dnf upgrade` — upgrade all packages
  - `sudo dnf remove <package>` — remove a package
- **Key Features**:
  - Improved dependency management over YUM
  - Faster downloads and installation
  - Supports plugins for extended functionality
  - Caching of metadata for efficiency

---

#### YUM (Yellowdog Updater Modified)
- **Distributions**: Older Fedora, CentOS, and RHEL versions
- **Package Format**: `.rpm`
- **Common Commands**:
  - `sudo yum check-update` — check for updates
  - `sudo yum install <package>` — install a package
- **Key Features**:
  - Older tool, gradually replaced by DNF
  - Simple interface but lacks some advanced features of DNF

---

#### Zypper
- **Distributions**: openSUSE, SUSE Linux Enterprise
- **Package Format**: `.rpm`
- **Common Commands**:
  - `sudo zypper refresh` — refresh repository metadata
  - `sudo zypper install <package>` — install a package
  - `sudo zypper update` — update system packages
  - `sudo zypper remove <package>` — remove a package
- **Key Features**:
  - Efficient patch management and security updates
  - Flexible repository handling
  - Supports interactive and non-interactive modes

---

#### Pacman
- **Distributions**: Arch Linux, Manjaro
- **Package Format**: `.pkg.tar.zst`
- **Common Commands**:
  - `sudo pacman -Syu` — update system packages
  - `sudo pacman -S <package>` — install a package
  - `sudo pacman -R <package>` — remove a package
- **Key Features**:
  - Lightweight and fast
  - Access to bleeding-edge software versions
  - Integration with AUR (Arch User Repository) for community packages

---

#### Snap
- **Supported On**: Ubuntu, Fedora, Arch Linux, Debian, and others
- **Package Format**: Snap packages
- **Common Commands**:
  - `sudo snap install <package>` — install a Snap package
  - `sudo snap refresh` — update all Snap packages
- **Key Features**:
  - Cross-distribution package format
  - Contains all dependencies within a single package (sandboxed)
  - Popular for delivering universal Linux apps

---

#### Flatpak
- **Supported On**: Most major Linux distributions
- **Common Commands**:
  - `flatpak install <package>` — install a Flatpak package
  - `flatpak update` — update Flatpak packages
- **Key Features**:
  - Cross-platform package management
  - Sandboxed applications for added security
  - Uses the Flathub repository for a wide selection of applications

---

### 3. Summary Table

| Package Manager | Supported Distros                | Package Format      | Key Features                              |
|-----------------|----------------------------------|---------------------|-------------------------------------------|
| **APT**         | Debian, Ubuntu, Linux Mint       | `.deb`              | Easy to use, resolves dependencies        |
| **DNF**         | Fedora, RHEL, CentOS (v8+)       | `.rpm`              | Fast, reliable, plugin support            |
| **YUM**         | Older Fedora, CentOS, RHEL       | `.rpm`              | Simple, legacy systems                   |
| **Zypper**      | openSUSE, SUSE                   | `.rpm`              | Patch management, flexible repositories   |
| **Pacman**      | Arch Linux, Manjaro              | `.pkg.tar.zst`      | Lightweight, bleeding-edge software       |
| **Snap**        | Ubuntu, Fedora, Debian, Arch     | Snap (sandboxed)    | Cross-platform, includes dependencies     |
| **Flatpak**     | Most major distributions         | Flatpak (sandboxed) | Sandboxed, universal apps via Flathub     |










## 2. Визначте який менеджер пакетів використовує ваш дистрибутив Linux. Опишіть основні команди для роботи з ним. (Краснопір Богдан)

  Curently i'm using Kali Linux. It is Debian based distro, so it have APT package manager, like Ubuntu or other.

  The basic comands to work with APT:

  1. sudo apt install _назва пакету_ - виконує встановлення нового пакету в систему.
  2. sudo apt install _назва пакету1_ _назва пакету2_ _назва пакету n_ - виконує встановлення одразу декількох пакетів за виконання одної команди. Пакети встановлюються почергово.
  3. sudo apt install ./_назва файлу_ - виконує встановлення файлу за його назвою.
  4. sudo apt install _назва пакету_=_версія пакету_ - виконує встановлення певної версії пакету.
  5. sudo apt remove _назва пакету_ - видаляє пакет. Так само, як і команди для встановлення, можна одразу видалити декілька пакетів.
  6. sudo apt autoremove - видаляє всі непотрібні пакети автоматично.
  7. sudo apt purge _назва пакету_ - видаляє пакет разом з файлами конфігурації. Також можливо видалити таким чином одразу декілька пакетів.
  8. sudo apt update - оновлює всі пакети в системі, змінюючи їх.
  9. sudo apt list --upgradable - виводить список пакетів, що можна оновити.
  10. sudo apt upgrade - оновлює пакети, заміняючи їх на нові. В кінці можна дописати назву пакету для оновлення лише того пакету.
  11. sudo apt dist-upgrade - оновлює пакети, що не можуть бути оновлені через оновлення інших пакетів, адже вони можуть повпливати на роботу цих програм.
  12. sudo apt list - виводить список всіх доступних пакетів для встановлення.
  13. sudo apt list --installed - виводить список всіх встановлених пакетів.
  14. sudo apt -qq list _назва пакету_ - показує, чи пакет встановлений в системі.
  15. sudo apt policy _назва пакету_ - показує версію пакету та з якого репозиторію він був встановлений.
  16. sudo apt search _назва пакету_ - шукає пакет в репозиторії.
  17. sudo apt show _назва пакету_ - виводить повну інформацію про пакет.
  18. sudo apt help - виводить основну інформацію про роботу з командою.

  To add a new repository, you need to add gpg-key firstly. After adding, you can run these comands to work with repository:

  - sudo apt-add-repository '_посилання на репозиторій_' - додає новий репозиторій до директорії.
  - sudo apt-add-repository --remove '_посилання на репозиторій_' - видаляє репозиторій.
  - sudo apt autoclean - очищує систему та видаляє непотрібні пакети разом з непотрібними репозиторіями.

## 3. Встановіть у терміналі через менеджер пакетів на свою систему. (Краснопір Богдан)
  
  I've installed the VLC media player as an example.

#### Instalation of VLC:

  First we enter `sudo apt install vlc`. After we are confirming instalation by typing "y"
  
![image](https://github.com/user-attachments/assets/2202eb2c-dbcc-4fc8-ad85-eaaa4c30d7df)

  After instalation, we can find VLC player in our App Manager:
  
![image](https://github.com/user-attachments/assets/e1b0b0ef-8229-409a-8338-2ff51a55f4a7)

  To test if player works correctly, i've opened sound file with .flac format and it's playing it without problem:

![image](https://github.com/user-attachments/assets/b52c264e-f434-43c1-999d-7b929dad65af)

#### Instalation of IDE for programing language have the same proces, as before. The only diference is that your program may not be founded in standard repository, so you'll need to add a new one, that contains needed program. Process of instalation also can be simplyfied by using a software store.


## 4. Яким чином можна встановити нові програми через магазини додатків та менеджери пакетів у графічному середовищі. Наведіть свої приклади. (Микитенко Назарій)
For example, in Windows, to install new applications using the licensed Microsoft Store: open the Start menu, launch the Microsoft Store, enter the name of the desired application in the search field and click the Install button, after which the application will download and install automatically. A similar process is used on Mac computers to install applications using the App Store, which can be opened from a document or through the Applications folder. The search for the desired application works in a special field, after which the user clicks the Get button and confirms the installation. Graphical package managers are often used in Linux distributions. For example, Ubuntu uses the GNOME software, where applications can be searched for and installed using a simple interface, and in Kubuntu a similar function is performed by Discover. In addition, on mobile devices, applications are installed through official stores: in iOS - through the App Store, and in Android - through Google Play. In these cases, we can enter the name of the desired application in the search field and click the Install button, so it provides easy and quick access to the necessary software.
