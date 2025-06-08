## 1. В ході роботи досить часто виникає завдання планування задач: (Микитенко Назарій)

#### Основні функції планувальника завдань в ОС

-	Запуск процесів, сценаріїв чи програм у визначений час (один раз, щоденно, щотижнево тощо).
-	Реагування на події системи (завантаження/відключення користувача, зміни мережевого статусу, створення файлів тощо).
-	Виконання завдань від імені конкретних користувачів чи груп із заданим рівнем привілеїв.
-	Запис результатів виконання (успіх/помилка) в журнали; надсилання сповіщень (email, системні повідомлення).
-	Налаштування повторних запусків при невдачі; визначення порядку (залежностей) між завданнями.
- Обмеження CPU, пам’яті або часу виконання для окремих завдань.

#### Порівняння планувальників Windows та Linux

|Функція / Можливість|Windows Task Scheduler|Linux (cron + systemd timers)|
|-|-|-|
|Інтерфейс налаштування|Графічна MMC-консоль, PowerShell, schtasks|Текстові файли crontab, CLI; GUI (gcrontab)|
|Тригери|Розклад, події (логін, idle, системний), зміни файлової системи|cron: тільки за розкладом; systemd: події D-Bus, таймери|
|Контекст виконання|Будь-який користувач, в режимі SYSTEM|Від імені користувача, root; systemd таймери від systemd-unit|
|Логування|Windows Event Log|Стандартні логи syslog/journal; власні файли|
|Умови запуску|Залежність від стану мережі, живлення, блокування екрану|cron: обмежені опції; systemd: багаті умови (OnCalendar, OnActiveSec, ConditionXYZ)|
|Обмеження ресурсів|Через Job Objects, локальні політики|nice, ionice, cgroups (через systemd)|
|Повторні спроби|Налаштування|cron: потребує зовнішніх скриптів; systemd: Restart= в юніт-файлі|
|Альтернативи/розширення|Планувальник SQL Server Agent, Azure Logic Apps|anacron, fcron, batch, at, systemd timers|


#### Планувальник Cron в Linux

1.	Основні принципи роботи
-	Демон cron постійно працює у фоні й перевіряє файли розкладу (crontab) кожну хвилину.
-	Кожен рядок crontab описує час запуску (5 полів) та команду.
-	Після спрацювання cron запускає команду в оболонці /bin/sh користувача, чий crontab використовується.

2. Формат запису в crontab

![Screenshot_2](https://github.com/user-attachments/assets/74b98d15-3357-4cfb-849b-ba5ac1e87b30)

3. Налаштування crontab

3.1 Редагування для поточного користувача

    crontab -e

3.3	Перегляд розкладу

    crontab -l

3.5	Видалення всіх завдань

    crontab -r

3.6	Системні crontab-файли

	/etc/crontab – дозволяє вказувати користувача;
 
	директорії /etc/cron.d/, /etc/cron.hourly/, /etc/cron.daily/ тощо.



#### Альтернативи cron і їх характеристика

1.	Anacron
   
-	Призначення: виконання завдань з мінімальною періодичністю «щоденно», «щотижнево» незалежно від того, чи був увімкнений комп’ютер у заданий час.
-	Механізм: перевіряє, чи завдання пропущено, і виконує його при наступному завантаженні.
-	Реалізація: окремий демон; завдання задаються в /etc/anacrontab.
-	Обмеження: не підтримує точний час, лише періодичність у днях.
  
2.	Fcron
   
-	Призначення: поєднує можливості cron та anacron; підходить для систем, що працюють нерегулярно.
-	Механізм: запускає завдання або в заданий час, або при наявності пропущених.
-	Особливості: гнучкіший синтаксис, залежності між завданнями, інтервал у хвилинах/секундах.
  
4.	Systemd-таймери
   
- Призначення: сучасна заміна cron на системах з systemd.
- Механізм: використовує одиниці типу .timer і .service.
- Переваги:
  
1. Багаті умови запуску (OnCalendar, OnActiveSec, OnBootSec).

2. Краща інтеграція з логуванням через journal.

3. Керування ресурсами через cgroups.

4. Низка опцій: Restart, Accurate, RandomizedDelaySec тощо.




## 2. Для вашої віртуальної машини зі встановленою ОС Linux здійсніть планування обраних вами задач (запуск додатків, вмикання/вимикання машини, очистка каталогів, видалення файлів, резервне копіювання, архівування тощо на ваш вибір) через планувальник Cron (Краснопір Богдан)
### - Виконання спланованої задачі в чітко визначений Вами час.

To schedule the process we need to edit crontab file or create it if is's not exist. So to do it we need to write down schedule parameters in our crontab file. 
In my exampe, i set the special time to a `echo` command:

![зображення](https://github.com/user-attachments/assets/e7bf70bf-db11-412f-b239-41982a77e135)

In our case, Asterisk * symbol means that command can be ran at any day of any week of any month.

### - Виконання однієї й тієї ж задачі двічі в день (час також визначаєте самостійно).

I'll use same command as the first time. To make this command run twice a day, we need to write different time, separated with coma. Example:

![зображення](https://github.com/user-attachments/assets/52939c18-0438-4c6c-bcf6-029a9fdbaa68)

Our command will run everyday at 12 o'clock and 18 o'clock.

### - Виконання однієї й тієї ж задачі тільки в будні (або тільки у вихідні дні) у чітко визначений проміжок часу (наприклад з 8 до 18 години).

To complete task in certain time range we need to set it by writing two values separated with hyphen (for example, 9-18).

To complete task only on weekdays, we need to set value of DOW from 1 to 5. For weekends we use 6-7/0 (7 and 0 means Sunday)

Example:

![зображення](https://github.com/user-attachments/assets/cf69451f-cfa1-4719-8064-131bd091c85b)

Our task will only run from 6 o'clock till 12 o'clock only from Mondat to Wednesday.

### - Виконання задач тільки раз у рік, раз у місяць, раз у день, щогодини, при вмиканні (після перезавантаження).

To make it possible, you can create new schedule with special strings instead of certain time. Here are they:

|Special String|Meaning|
|-|-|
|@reboot|	Run once, at system startup|
|@yearly| Run once every year, “0 0 1 1 *”|
|@annually| same as @yearly|
|@monthly| Run once every month, “0 0 1 * *”|
|@weekly| Run once every week, “0 0 * * 0”|
|@daily| Run once each day, “0 0 * * *”|
|@midnight| same as @daily|
|@hourly |	Run once an hour, “0 * * * *”|

Example:

![зображення](https://github.com/user-attachments/assets/91d4ff02-b98e-408b-9321-8d89c23b8ca7)

Завдання 3.

![Image](https://github.com/user-attachments/assets/1aeb0a3d-357f-46f3-9432-fa983d842747)

