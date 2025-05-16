## Завдання для попередньої підготовки (Микитенко Назарій)


## Відповіді на контрольні запитання (Краснопір Богдан) 

### 1. Як пов'язані між собою команди cat та tac? 

Вони дуже схожі за призначенням: за основним призначенням `cat` виводить зміст файлу в термінал, а `tac` робить те ж саме, тільки в зворотньому порядку.

### 2. Що робить команда ss?

The `ss` command is used to view socket statistics (інформації про мережеві з'єднання) and very similar to `netstat`. It's better to use `ss` when we need some information in faster way and better to use `netstat` when we need more information about network.

### 3. В чому відмінність між командами ps --forest та pstree?

These commands is doing the same, but displays information in diferent way:

`pstree` is displaying parrent-child relations between two processes, like this:

![зображення](https://github.com/user-attachments/assets/f1d21850-0a30-4ba8-abab-c823c947319e)

`ps --forest` is displaying relations like a tree, where child processes are connected to parrent processes. It also shows process PID and time:

![зображення](https://github.com/user-attachments/assets/f838ba9f-49bd-4eee-9e79-2cbaafbc787e)

### 4. У яких каталогах зберігаються налаштування системи?

System configurations are located in few directories: /etc (services, network and hots configurations) /var (custom variables), users /home directory (special user configurations) and /opt (custom software configurations).

### 5. У яких каталогах можна знайти встановлені в системі програми, доступні для користувача?

Встановлені програми можна знайти в таких каталогах: /usr/bin - для основних користувацьких програм; /usr/local/bin - програми, що були встановлені вручну; /opt - не завжди, але програми можуть зберігатися тут.

### 6. У яких каталогах можна знайти встановлені системні програми і програми призначені для виконання суперкористувачем?

Системні програми можуть зберігатися: /bin - основні команди для всіх користувачів; /usr/bin; та бібліотеки до них - /lib або /lib64

Програми, призначені для суперкористувача, часто зберігаються в каталогах, назва яких починається на s. Такими каталогами є: /sbin - містить команди для суперкористувача; /usr/sbin - додаткові системні утиліти суперкористувача; /usr/local/sbin - локальні системні утиліти суперкористувача; /root - домашній каталог суперкористувача.

Крім цього, можна окремо задати обмеження доступу або до певного каталогу вручну.

### 7. Поясніть призначення команд ping, ifconfig, traceroute.

`ping` is used when we need to check if we can establish connection to any host. When we use it, our host (host1) is sending packets to other host (host2). When host2 gets our packet, it must reply us, but if don't - nothing happens. So, if we got reply - connection is established, but if we didn't got reply - there was a ploblem with connection.

`ifconfig` is used to display network configuration information, such as: our IP address, connected IP addresses, netmask, connection type and other.

`traceroute` is used to view the way that our packet is being tranfered from us to other IP address or domain. It shows all intermediate devices, such as router, switch, hub and other.

### 8. Як називаються мережеві інтерфейси в Linux?

В основному мережеві інтерфейси називаються їх скороченими назвами або абревіатурами за призначенням. В кінці інтерфейсу додається його порядковий номер, починаючи з 0. 

Приклади: eth0 - провідне з'єднання за допомогою протоколу Ethernet з порядковим номером 0, lan5 - з'єднання з хостом в локальній мережі, для нашого хоста це з'єднання буде п'ятим за рахунком (до цього були з'єднання з меншими числами).

### 9. Як за допомогою команди ifconfig вивести параметри тільки одного мережевого інтерфейсу (наприклад, eth1), а не всіх?

Для того, щоб вивести параметри лише певного мережевого інтерфейсу, треба після команди `ifconfig` вказати його назву. Це матиме такий вигляд: `ifconfig eth1`. Замість eth1 пишемо іншу потрібну назву інтерфейсу.

## Висновок (Микитенко Назарій)
