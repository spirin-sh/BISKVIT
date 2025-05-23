## 1. В ході роботи досить часто виникає завдання планування задач: (Микитенко Назарій)
- Охарактеризуйте основні функції які може виконувати планувальник завдань в будь-якій ОС. Порівняйте можливості планування завдань в різних ОС на прикладі Windows та Linux.
- Опишіть основні принципи роботи з планувальником Cron в ОС Linux. Як його налаштовувати? Чи є йому альтернативи (дайте їх характеристику).

## 2. Для вашої віртуальної машини зі встановленою ОС Linux здійсніть планування обраних вами задач (запуск додатків, вмикання/вимикання машини, очистка каталогів, видалення файлів, резервне копіювання, архівування тощо на ваш вибір) через планувальник Cron (Краснопір Богдан)
### - Виконання спланованої задачі в чітко визначений Вами час:

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

