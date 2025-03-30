# Лабораторна робота №7

## Тема: Створення скриптових сценаріїв та визначення апаратної конфігурації системи

## Мета: 

1.Отримання практичних навиків роботи з командною оболонкою Bash.

2.Знайомство знайомство з базовими діями при роботі зі скриптовими сценаріями.

## Завдання для попередньої підготовки (Краснопір Богдан)

### Словник термінів:

**#! (shebang)** - команда, що визначає шлях до оболонки, якщо вписана на початку скрипту.

**Скрипт (Script)** - це файл, в якому міститься послідовний набір команд, що можуть бути виконані, в нашому випадку, в оболонці. Даний термін також використовується в програмуванні. 

**Змінні (Variables)** - цезначення, що набуває певного числового чи символьного значення та над яким прододяться певні дії.

**Умови (Conditionals)** - це оператори, що виконують дії над змінними за певної умови (if, else).

**Цикли (Loops)** - оператори, що виконують дії над змінними за певної умови циклічно, тобто допоки виконується умова (for, while,).

**Шина (Bus)** - високошвидкісне з'єднання, що дозволяє обмінюватися інформацією між комп'ютерами або компонентами всередині комп'ютера.

**Драйвера (drivers)** - програмне забезпечення, що дозволяє компонентам комп'ютера обмінюватися інформацією з операційною системою.

**Partition** - логічне розділення диску, тобто розбиття його на менші сигменти.

>Також в розділах 11 та 12 були вказані терміни, що ми раніше вчили (на приклад CPU, RAM, SSD, команда echo, та деякі інші). Тому вони не будуть тут вказані

### Відповіді на питання:

#### 1. Охарактеризуйте поняття скриптового сценарію у командній оболонці.

Script scenario is a set of commands that is written on file, so shell can run them adherently. 

Scripting, the process of creating scipts, is can be called programming in some case. Because it uses programing language, so it have it's own syntax, you can create variables and work with them by using operators. 

The main difference between script and program is that program is the main proccess or system, but script is code, that acts upon this system. So the script can be dissabled without dissabling program or system.

The main purpose to use scripts in shell is to automate some processes, like finding specific file.

#### 2. Яким чином створюються та редагуються скрипти, що треба зробити щоб запустити скрипт.

Для створення скриптів використовують редактори файлів для командного рядку Nano чи Visual Editor. Також можливо створити скрипт просто через текстовий файл.

Спершу потрібно вказати шлях до оболонки (для дуже простих скриптів це не обов'язково). Для цього в першому рядку скрипта повиннен бути вказаний шлях до оболонки з префіксом #! Приклад: #!/bin/sh - вказує шлях до оболонки bash. Дія необхідна, адже існують різні оболонки і дуже часто кожна має власний синтаксис.

Потім можна вписувати команди для виконання. Крім системних команд також існують оператори, як for, whie, if, esle. Тому треба знати поняття змінної, оператора, циклу.

Після створення, його потрібно запустити. Щоб це зробити, можна використати команду `sh text.sh`, де текстовий файл представляє скрипт, або напряму через шлях - `./text.sh`

> Треба зазначити, що при виконанні через шлях може виникнути проблення у відсутності прав доступу. Вразі цього для зміни доступу використовуємо команду chmod, приклад: `chmod +x ./text.sh`

#### 3. Які основні компоненти материнської плати ви знаєте?

The basic components of motherboard:

1. Socket - where CPU is holded
2. Chipset - manages comunication between computer components (CPU, GPU, RAM, etc)
3. BIOS/UEFI chip - where the BIOS or UEFI is located.
4. CMOS battery - battery that powers BIOS/UEFI when the computer is off. Purpose of doing it is to save custom configuration and run system clock when PC is off.
5. Expansion slots - used to connect GPU, sound cards, network addapters.
6. RAM slots - holds Random Access Memory sticks.
7. Storage connectors - used to connect HDD, SSD, M2 SSD or other memory devices. Example of connectors: ATA, SATA, M2.
8. Power connectors - used to power up certain computer components.
9. Input/Output ports - used to connect peripheral devices: monitor, keyboard, mouse, microphone, etc.

#### 4. Коротко охарактеризуйте для яких пристроїв оперують поняттями MBR та GPT?

Дані поняття використовуються для пристроїв збереження даних, як от HDD чи SSD. Дані поняття визначають як буде виконана робота з дисками: їх розбиття, форматування та інші.

Основною відмінністю Master Boot Record MBR та GUID Partiton Table є те, що GPT прийшла на заміну MBR, адже дана технологія є старшою і нормально працює з об'ємом пам'яті не більше ніж 2 ТБ, також не може створювати більше чотирьох розділів та сумісний в основному зі старими системами. GPT ж може працювати з об'ємом понад 2 ТБ, створювати 128 розділів, є більш стійким до пошкоджень і загалом є кращим вибором для нових систем.

#### 5. В чому суть операції монтування, для чого вона потрібна?

Монтування - це процес підключення файлової системи носія даних (HDD чи SSD) до операційної системи. Без даної процедури ОС не зможе бачити диск, зчитувати чи редагувати дані диску. Монтування може бути виконане автоматично або вручну. Здебільшого вручну монтування виконується на Linux. 

В Linux монтування носіїв виконується до певної точки монутвання дерева. Цією точкою може бути спеціальний каталог. Монтування можливе лише до існуючого каталогу. Цікаво також те, що монтування в Linux для портативних пристроїв, як от CD-диск чи флеш-накопичувач, виконується до каталогу /media.




## Хід роботи (Клімчук Ярослав)
### Таблиця для команд
#### vi Editor Commands

| Command/Key | Function |
|------------|----------|
| `vi myfile` | Open or create the file `myfile` in the vi editor |
| `:wq` | Save the file and exit |
| `dw` | Delete a word |
| `u` | Undo the last operation |
| `xxxx` | Delete four characters one by one |
| `4u` | Undo the last four operations |
| `dd` | Delete the current line |
| `p` | Paste the deleted lines below the current line |

#### Navigation and Editing in vi

| Key/Command | Function |
|------------|----------|
| `1G` | Go to the beginning of the file |
| `i` | Enter insert mode |
| `l` | Move one character to the right |
| `~` | Toggle case (lowercase ⇄ uppercase) |
| `j` | Move down one line |
| `10l` | Move 10 characters to the right |
| `a` | Enter insert mode after the cursor |
| `:x` | Save and exit |
| `:wq` | Write to file and quit |
| `:wq!` | Force write to a read-only file and quit |
| `ZZ` | Save and exit (without `:`) |
| `:q!` | Exit without saving |
| `:e!` | Discard changes and reload the file |
| `:w!` | Force write to a read-only file |

#### Linux System Commands

| Command | Description |
|---------|------------|
| `lscpu` | Display CPU information |
| `head -n 20 /proc/cpuinfo` | Show the first 20 lines of the `/proc/cpuinfo` file |
| `free -m` | Display RAM and swap usage in megabytes |
| `free -g` | Display RAM and swap usage in gigabytes |
| `lspci` | List connected PCI devices |
| `lsusb` | List connected USB devices |
| `lsmod` | View currently loaded kernel modules |
| `fdisk` | Manage disk partitions |

3.![Image](https://github.com/user-attachments/assets/17696c2d-9669-473f-948f-1396efa24024)

![Image](https://github.com/user-attachments/assets/eb0ee609-bea3-45b4-a434-d9a8c784f325)

![Image](https://github.com/user-attachments/assets/b2915bda-9e87-4e10-bac6-849954e4f4de)

3.2 Приклад своєї програми

![Image](https://github.com/user-attachments/assets/b520cae5-a801-4728-bd84-786eb7d54942)

![Image](https://github.com/user-attachments/assets/151689d3-e046-45a3-8f18-5c0def3b6b79)

![Image](https://github.com/user-attachments/assets/d50ee0e8-0e69-416d-9914-18c2bdc5ff5f)




## Контрольні запитання (Микитенко Назарій)

**1**.	В чому відмінність між командами arch та lscpu?

The *arch* command in Linux displays the processor architecture. The *lscpu* command, on the other hand, provides detailed information about the processor, including architecture, operating modes (32-bit or 64-bit), manufacturer, model, number of cores, threads, and cache sizes.


**2**.	Якою командою можна отримати інформацію про стан використання RAM поточною системою?

You can use the *free -h* command to get information about the RAM usage status of the current system.

**3**.	*Яким чином у скриптах можна опрацьовувати змінні та створювати розгалужені та циклічні сценарії?

In Linux shell scripts, variables are created by assigning values: *variable_name=value*, and accessed via *$variable_name*. Branching is implemented using *if* and *case* constructs. *For*, *while*, and *until* loops are used to repeatedly execute blocks of code.

**4**.	*Які команди для перегляду стану підключення периферійних пристроїв можна використати в терміналі? 

In the Linux terminal, you can use commands such as *lsusb* (for USB devices), *lspci* (for PCI devices), and *dmesg* (to view kernel system messages) to check the connection status of peripherals.


**5**.	**Які можливості застунку gparted? 

GParted is a graphical partition editor for Linux that allows you to create, delete, resize, move, verify, and copy disk partitions and their file systems. It is useful for making space for new operating systems, reorganizing disk usage, copying data, and creating disk images. GParted supports various file systems, including *ext2, ext3, ext4, FAT16, FAT32, HFS, HFS+, JFS, Linux-swap, ReiserFS, Reiser4, UFS, XFS, and NTFS.*

## Висновки
During the laboratory work, the basics of working with the Bash command shell were examined, in particular, creating and executing scripts. The basic commands for editing text files in the vi editor were introduced, as well as system commands for obtaining information about the computer's hardware. A custom script was created that demonstrates the use of variables, conditional operators, and loops. The basic concepts related to file systems, disk partitions, and connecting peripheral devices were also examined.
