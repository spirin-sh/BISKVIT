# Лабораторна робота №9

## Тема: Захист системи та користувачів у Linux. Створення користувачів та груп.

## Мета: Отримання практичних навиків роботи з командною оболонкою Bash. Знайомство з базовими діями при створенні нових користувачів та нових груп користувачів.

## Завдання для попередньої підготовки (Краснопір Богдан)

### Словник базових термінів:

- UID (User ID) - номер користувача, для звичайних користувачів він має бути більше 500 (в деяких системах - більше 1000), для системних аккаунтів - від 1 до 499, для суперкористувача **root** це значення рівне 0.
- System Accounts - це системні аккаунти, які призначені не для використання звичайними користувачами, а для робочих сервісів системи.
- UPG (User Private Group) - спеціальна група, що створюється при створенні нового користувача і називається його іменем. Працює не на всіх дистрибутивах.
- GID (Group ID) - ID номер групи, що призначений для їх розрізнення в системі. Лише один GID може бути для одної групи.

### Відповіді на питання:

#### Розкрийте поняття UPG, коли їх доцільно використовувати?

UPG (User Private Group) - це спеціальна група користувачів, що містить лише новоствореного користувача і носить його назву. Їх доцільно використовувати коли необхідно створити нового користувача зі специфічним наборо правил, які матиме лише він. Або для простого створення нічим не пов'язаних користувачів. UPG забезпечує ізоляцію від спільних каталогів користувачів і створення каталогу власної групи.

#### *Якими командами можна створити групи користувачів? Наведіть приклади

Основною командою при створенні групи користувачів є `groupadd`. 

Її потенціал можна розширити за допомогою параметрів, таких як: -g (дозволяє задати групі власний GID), -r (для можливості задати GID менше 500 або 1000, залежно від дистрибутиву)

Приклад: створення групи користувачів із назвою students, що матиме GID рівний 1572: `groupadd -g 1572 students`

Приклад: створення групи користувачів із назвою guys, що матиме GID менше 1000: `groupadd -r guys`

#### **Якими командами можна змінити налаштування груп користувачів? Наведіть приклад

Основною командою для цього є `groupmod`, але її потенціал також розкриваєтсья з використанням параметрів: -n (для зміни імені групи), -g (для зміни GID групи)

Приклад: зміна імені групи students на notastudents: `groupmod -n notastudents students`

Приклад: зміна GID групи students з початкового значення на 1101: `groupmod -g 1101 students`

> ЗМІНА GID МОЖЕ ПРИЗВЕСТИ ДО ТОГО, ЩО ВСІ ФАЙЛИ, АСОЦІОВАНІ З ЦІЄЮ ГРУПОЮ, НЕ БУДУТЬ ДОСТУПНІ В НІЙ

## Хід роботи (Микитенко Назарій)

#### 2. Таблиця команд

|Назва команди|Її призначення та функціональність|
|-------------|----------------------------------|
|id|Показує UID, GID та групи поточного або вказаного користувача|
|head|Виводить перші 10 рядків файлу|
|grep|Пошук рядків, що відповідають шаблону, у файлі або потоці даних|
|ls|Перегляд вмісту каталогу|
|getent|Вивід записів з баз даних|
|who|Показує, хто увійшов у систему|
|w|Показує, хто увійшов у систему і чим займається|
|last|Виводить історію входів користувачів у систему|
|groupadd|Створює нову групу|
|groupmod|Змінює параметри існуючої групи|
|groupdel|Видаляє існуючу групу|
|useradd|Створює нового користувача|
|usermod|Змінює параметри існуючого користувача|
|userdel|Видаляє користувача|
|passwd|Змінює пароль користувача|
|nano|Проста текстова консольна програма для редагування файлів|
   
#### 3. Практичні завдання

Вивід інформації різними способами

![1](https://github.com/user-attachments/assets/b25b3578-2259-494f-af14-916b4d13498b)


Команди last, w, who, їх порівняння


*Команда last - показує час входу та історію*

*Команда w - показує показує час входу та показує що робить*

*Команда who - показує тільки час входу*


![2](https://github.com/user-attachments/assets/1039ac34-a018-424d-93ee-8b6bfdd5aaf6)


Створення груп та їх ідентифікатори

![3](https://github.com/user-attachments/assets/27c3e5c4-bac0-4a76-9271-a24336e84259)


Створення користувачів

![4](https://github.com/user-attachments/assets/dbb42e6b-70d7-4f00-b764-eba5d413da8c)


Додавання користувачів до груп

![5](https://github.com/user-attachments/assets/58237407-f9d4-404d-8056-1d94402ea3a8)


Перегляд інформації про групи

*Рядок містить назву групи, GID та список користувачів, які до неї належать.*


![6](https://github.com/user-attachments/assets/904024cf-5295-459c-8979-d69dc0385329)


Видалення першого, другого та третього користувачів

*Інформація про першого, другого та третього користувачів після видалення не залишилась.*

![7](https://github.com/user-attachments/assets/bb94add8-8aa9-46d3-a74a-2230db7cb1d4)


Перегляд інформації про існуючі групи 

![8](https://github.com/user-attachments/assets/44ee4d93-2431-4bc9-a7bf-e439715c64bc)


Видалення створених груп

![9](https://github.com/user-attachments/assets/7fff8ef0-b10c-4783-980d-29cae3ae88f5)


Перегляд інформації про існуючі групи користувачів

![10 2](https://github.com/user-attachments/assets/bdab3fa6-9081-47f6-a48c-2b11d2d3c755)

## Відповіді на контрольні питання (Клімчук Ярослав)

### 1. Why are passwords not stored in plain text in configuration files?
Passwords are sensitive data. Storing them in plain text would make them easily accessible to anyone who gains access to the file system. To protect against unauthorized access, passwords are hashed and stored in secure files such as /etc/shadow. This way, even if someone accesses the file, they cannot directly retrieve the original password.

### 2. Why is it not recommended to perform everyday operations using the root account?
Logging in as root is dangerous because:

All processes run with unrestricted privileges, increasing the risk of system damage from mistakes.

You may forget you're logged in as root and unintentionally run harmful commands.

Applications like browsers or email clients run without restrictions, increasing the risk of exploits.

Graphical environments running as root are especially vulnerable since many programs are executed with full privileges.
Because of these risks, many distributions (like Ubuntu) disable root login and encourage using sudo instead.

### 3. What is the difference between su and sudo for obtaining elevated privileges?

su switches the user to another account (commonly root) and requires the root password.

sudo allows a regular user to run specific commands with root privileges using their own password, as configured in /etc/sudoers.
This makes sudo more secure and auditable, since all usage is logged.

### 4. Why is the root user's home directory not located under /home?
The root user's home is /root to isolate it from regular user data. This improves system reliability and security:

If /home is on a separate partition and fails to mount, root still has access to its home directory.

Separation also avoids accidental exposure of system-critical files to regular users.

### 5. What is the purpose of the getent command?
getent is used to query administrative databases configured in /etc/nsswitch.conf, such as:

getent passwd → Shows user accounts.

getent group → Shows group accounts.
It supports both local and network-based authentication systems (like LDAP), making it useful for mixed environments.

### 6. How can a user's password be changed?
The passwd command is used:

Regular users: passwd → Changes their own password.

Root user: passwd username → Changes another user’s password.

### 7. How can existing groups be deleted? Will any information about them remain?
Use groupdel groupname to delete a group.
After deletion:

Group entries are removed from /etc/group.

Any files with the deleted group’s GID will still retain the numeric GID, but no name will be associated.

Users previously in the group will no longer have that group in their memberships.

### 8. What is the purpose of the chage command?
chage manages password expiration policies:

Set maximum and minimum password age.

Force password change at next login.

Lock accounts after a certain number of inactive days.

Example:

chage -l username 
chage -M 90 username  

### 9. What are the most commonly used usermod options?

-aG group1,group2 – Add user to additional groups (with -a to append).

-d /new/home – Set new home directory.

-s /bin/shell – Change login shell.

-L / -U – Lock or unlock account.

-c "comment" – Change the comment field.

-g gid or -G groupnames – Change primary or secondary groups.

