## 1. В робочому просторі операційної системи необхідно встановити декілька командних інтерпретаторів (Краснопір Богдан)

### Процес встановлення

Для встановлення додаткового командного інтерпретатора нам необхідно виконати такі команди (Для Ubuntu та Debian):

Для початку оновлюємо всі пакети командою `sudo apt update`

Після чого виконуємо встановлення обраного інтерпретатора командою `sudo apt install ksh` (Замість KornShell ksh вписуємо назву будь якого інтерпретатора).
В моєму випадку, я буду виконувати встановлення fish та tcsh.

### Коротка характеристика fish та tcsh

fish (Friendly Interactive Shell) - оболонка, що розвивається як дружня до користувача та проста у використанні. Вона підтримує можливості, такі як підсвічування синтаксу, автоматичне виправлення помилок при вводі та автоматичне доповнення команд параметрами. У ній було багато чого спрощено, починаючи від процесу написання сценаріїв, і закінчуючи синтаксисом. Якщо підсумувати, то fish дуже спрощує роботу в терміналі та позиціонує себе як заміну складнішим bash та zsh.

tcsh (TENNEX C Shell) - оболонка, що базується на старішій csh та має зворотню сумісність з нею (тобто, скрипти написані для tsch будуть працювати в csh і навпаки). В порівнянні зі старшою оболонкою, ця має досить багато нововведень, такі як: історія команд, можливість редагування коду всередині командного рядку, автозаповнення, можливість створення псевдонімів для команд та унікальна можливість роботи з ними. Основною відмінність tchs та csh від bash є те, що синтаксис у них дуже подібний до мови програмування "C".

## 2. Необхідно створити 10 нових користувачі в вашій системі та розподілити їх по групам (Краснопір Богдан)

Firstly, we need to create new groups, then we add users to them. To create a new usergroup we use command `sudo addgroup <groupname>`. Is you need to delete existing group, use `sudo delgroup <groupname>`.
So, we created 5 groups of users: techsupport, developers, financiers, founders and guests; after this we create 10 users (in my example they will be called user1-user10).

To create a new user, we use command `sudo adduers <username>`. To mannage new user, use commands: `sudo usermod <username>` - editing existing user's details, `sudo passwd <username>` - change of user's password, `sudo userdel <username>` - deleting user. That's not all commands for user mannagement, but most used one's.

After creation of users, we are adding them to groups. To do it we use command `sudo usermod -aG <groupname> <username>`. We repeat the process with all users.

Example: after creation of user i use `group` command to see if user is added to group.

![зображення](https://github.com/user-attachments/assets/9a50f825-ab97-4724-9af5-93560e6b066d)

## 3. Надання командного інтерпритатора

![Image](https://github.com/user-attachments/assets/f09d6964-4f01-4bce-b1d0-494237d7ffc4)

![Image](https://github.com/user-attachments/assets/3afe85b6-5018-4d2b-a476-6e94bc4a1d1c)
