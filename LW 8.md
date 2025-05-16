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

## Висновок (Микитенко Назарій)
