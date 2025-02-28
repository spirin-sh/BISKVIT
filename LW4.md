# Лабораторна робота №4

## Тема: "Команди Linux для управління процесами"

## Мета: 
1. Отримання практичних навиків роботи з командною оболонкою Bash.
2. Знайомство з базовими командами для управління процесами.

## Завдання для попередньої підготовки (Краснопір Богдан)

### Словник базових термінів

**Інтерактивні процеси** - процеси, які запускаютсья лише за наявності користувача та за допомогою термінального сеансу. Не запускаються автоматично. Лише один процес цього виду може виконуватися одночасно.

**Фонові процеси** - процеси, що не підключені до терміналу та запускаються автоматично. Вони не чекають на завершення інших фонових процесів і можуть бути запущені паралельно один з одним.

**Демони (daemons)** - тип фонових процесів, що запускаються під час старту системи та працюють протягом усього сеансу. Вони запускаються як системні задачі. Прикладом є служба ел. повідомлень sendmail.

**Батьківські процеси** - процеси, що під час свого виконання створюють інші процеси.

**Дочірні процеси** - процеси, що створені іншими процесами.

#### Основні стани процесу:

1. **Виконання** — процес або запущений або готовий до запуску (очікує передачі на виконання процесору).
2. **Очікування** — процес очікує настання деякої події (користувацького вводу, сигналу від іншого процесу тощо) або виділення системних ресурсів.
3. **Завершений** — процес був зупинений, як правило, шляхом отримання сигналу штатного завершення роботи exit()
4. **Зомбі** — іноді, коли батьківський процес вбивається до завершення дочірнього процесу, дочірні процеси стають “осиротілими”, при цьому в якості нового батька (з відповідною зміною PPID) їм призначається процес init. Вбиті процеси, але які при цьому все ще відображаються в таблиці процесів, називають процесами зомбі

#### Визначення для кожної інформаційної колонки команд `ps` та `top`:

1. **Process ID (PID)** - ідентифікаційний номер процесу.
2. **TTY** - термінал, з якого був запущений процес.
3. **UID** - ідентифікаційний номер користувача.
4. **PPID** - ідентифікаційний номер батьківського процесу (тобто процесу, що запустив інший процес)
5. **STIME** - цас, коли процес був запущений.
6. **TIME** - час, необхідний для процесора щоб запустити процес.
7. **CMD**- назва запущеної програми
8. **F** - системні позначки, задані ядром для процесу.
9. **S** - стан процесу ( О - виконується, S - очікування, R - готовий до виконання, Z - зомбі, батькіський процес не доступний для завершення дочірнього процесу, T - процес зупинено)
10. **PRI** та **PR** - пріорітет процесу (більше число - менший пріорітет)
11. **ADDR** - адреса процесу в пам'яті.
12. **SZ** - приблизна кількість місця в пам'яті, необхідна для заміни розташування процесу.
13. **WCHAN** - адреса функції ядра, за якою процес знаходиться в стані сну.
14. **USER** - ім'я того, хто запустив процес (може включати як і звичайних користувачів, так і привілейованих ращом із системою)
15. **VIRT** - об'єм віртуальої пам'яті, що використовує процес.
16. **RES** - об'єм фізичної пам'яті, що використовує процес.
17. **SHR** - об'єм пам'яті, якою процес ділиться з іншими процесами.
18. **NI** - виставляє пріорітетність процесів.
19. **%CPU** - частка процесора, яку використовує процес.
20. **%MEM** - частка фізичної пам'яті, яку використовує процес
21. **TIME+** - показує скільки часу з моменту запуску процес використовує CPU
22. **COMMAND** - назва процесу за його командою.

> "Пам'ять" в даному випадку - це ресурс оперативної пам'яті RAM

#### Визначення сигналів процесу:

1. **HUP** (1) - "вішає трубку"
2. **INT** (2) - перериавє
3. **QUIT** (3) - зупинаяє запущений процес
4. **KILL** (9) - безумовно перериває процес "убиваючи" його
5. **SEGV** (11) - створює перешкоди для виконання
6. **TERM** (15) - перериває процес, якщо це можливо
7. **STOP** (17) - безумовно зупиняє роботу процесу, але не перериває його
8. **TSTP** (18) - призупиняє процес, але він продовжує роботу в фоновому режимі
9. **CONT** (19) - продовжує виконання процесу після сигналів STOP та TSTP

> Номер в дужках показує номер сигналу

### Відповіді на питання

#### 1. Які команди для моніторингу стану процесів ви знаєте. Як переглянути їх можливі параметри?

Команда ps показує процеси в даній оболонці. 
Для виведення додаткової інформації про процеси використовують різні параметри, типу -f (виводить більше інформації) або -l (виводить ще більше інформації).

Команда top виконує схожу функцію, але відображає інформацію про процеси в режимі реального часу, як диспетчер задач у Windows. Вона також має свої параметри.

Дізнатися можливі параметри команд можна декількома способами:

1. Через параметр `--help`, що показує короткі відомості про команду.
2. Через команду `man`, що показує всю інформацію про команду та її можливі параметри.
3. Через команду `info`, що містить більш докладну інформацію, ніж man-сторінка.

Також одним з варіантів можна вважати перегляд параметрів зі сторонніх ресурсів (Інтернет чи конспект)

#### 2. Чи може команда ps у реальному часі відслідковувати стан процесів?

Відповідь до цього питання - ні, не може. Вона лише зчитує інформацію один раз під час виконання і виводить її до нас. 
Цю функцію виконує команда `top`

#### 3. За якими параметрами можливе сортування процесів в команді top? Як переключатись між ними?

Сортування процесів можлива за такими параметрами: 
1. За використанням CPU - клавіша "P"
2. За використанням RAM - клавіша "M"
3. За його ID - клавіша "N"
4. За часом виконання - клавіша "T"
5. За зростанням чи спаданням - клавіша "R"

Кожна з клавіш називається "гарячою клавішою".

Крім цього можна натиснути Shift+F. Відкриється меню вибору поля для сортування, в ньому можна перемикатися за допомогою стрілок вверх/вниз, а для застосування виброру натисніть клавішу Enter.

#### 4. Які команди для завершення роботи процесів ви знаєте?

**kill** - посилає процесу команду завершення роботи за його ID

**pkill** - завершує процес за його ім'ям

**killall** - завершує декілька процесів за схожим ім'ям.



## Контрольні запитання (Микитенко Назарій)
**1.	Яке призначення директорії /proc в системах Linux. Яку інформацію вона зберігає?**

The */proc* command provides an interface for obtaining system and process information, and is also used to configure kernel parameters in real time. It stores process information, kernel and system information, and kernel settings.

**2.	Як серед будь-яких трьох процесів динамічно визначати, який з них в поточний момент часу використовує найбільший обсяг пам'яті? Який відсоток пам’яті він споживає від загального обсягу?**

To do this, periodically get the amount of memory used by three processes using the command *ps -o pid,comm,%mem,rss -p PID1,PID2,PID3*. The largest process will be in first place. 
To determine the percentage of memory out of the total, can use *free -m* or *grep MemTotal /proc/meminfo*, and then calculate the ratio.

**3.	Як отримати ієрархію батьківських процесів в системах Linux? Наведіть її структуру та охарактеризуйте.**

The hierarchy of parent processes can be obtained using the command *pstree -p, pstree -p username, pstree -sp <PID>*

### Структура ієрархії:

![alt text](https://media.discordapp.net/attachments/1079721811064913972/1345079738401820692/Screenshot_1.png?ex=67c33ea0&is=67c1ed20&hm=f5c99cfa019b64706fd9f478d5f1f08abc92f789c1ac920905239d2563e80405&=&format=webp&quality=lossless&width=435&height=341)

All processes originate from systemd or init, and each process has its own parent process, which can *fork()* child processes. 
If a process terminates but its status is not read by the parent process, it becomes a so-called *zombie*.

**4.	Чим відрізняється команда top від ps?**

*Ps* and *top* have two main differences:
1. *ps* provides a static snapshot of the state of processes, while *top* provides a dynamic, constantly updated display.
2. *ps* is designed to display information without the ability to interact, while *top* allows you to manage processes and configure the display of information in real time.


**5.	Які додаткові можливості реалізує htop в порівнянні з top?**

*htop* is an improved version of *top* with a color interface, graphical resource usage indicators, and convenient process management using the keyboard and mouse. 
It supports a tree view of processes, flexible column settings, fast search, and allows you to kill processes without entering the *PID* (making it easier to kill processes).

**6.	Опишіть компоненти вашої мобільної ОС для здійснення моніторингу запущених в системі процесів?** 

In my operating system (Android), monitoring of running processes is carried out using the components **Activity Manager, Process Stats, Linux Kernel**.
**Activity Manager** manages the life cycle of applications and monitors active processes.
**Process Stats** collects and analyzes process statistics, evaluates their performance and resource usage.
**Linux Kernel** is a kernel that provides low-level monitoring and management of processes through mechanisms such as the task scheduler and interprocess communication tools.

**7.	Чи підтримує Ваша мобільна ОС термінальне керування роботою процесів, опишіть як саме.**

If you use a tool like a terminal emulator, then yes, Android supports terminal process management. Since Android is built on the Linux kernel, it has a command shell available that can already be opened through a terminal emulator, for example: **Termux**.

**8.	Чи можливо поставити сторонні програмні засоби, що дозволяють організувати управління та моніторинг роботою процесів у Вашому мобільному телефоні. Коротко опишіть їх.**

This is possible, although modern versions of Android impose some restrictions due to security measures. For example, applications such as **3C Toolbox** or **SystemPanel 2** allow you to view the list of running processes, analyze RAM usage and CPU load, and perform basic management. Some advanced features (for example, access to system processes) may require root rights, since the standard Android architecture restricts third-party applications from accessing important system resources.

