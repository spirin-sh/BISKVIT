# Хід роботи (Краснопір Богдан)
## 1. Таблиця команд та їх опис
| Назва команди | Її призначення |
| --- | --- |
| ls | Виводить інформації про каталоги та файли. За замовчуванням без аргументів відображає інформацію для поточного каталогу |
| ls -l | Використанні параметру -l в команді ls дозволяє відобразити інформацію про файли, розташовані в поточному робочому каталозі, у довгому форматі, який надає більш розширену додаткову інформацію |
| ls -l /tmp | Використання аргументу /tmp в поєднанні з параметром -l в команді ls дозволяє відобразити детальну інформацію про файли в каталозі /tmp |
| ls -r | Завдяки параметру -r виводить інформацію про каталоги та файли у зворотньому порядку |
| ls -l -r або ls -lr | Виконує ту ж функцію, що й ls -l, але виводить інформацію в зворотньому порядку |
| ls -l -h | Відображає інформацію про файли та каталоги в розширеному форматі з переводом байтів у більш зрозумілі для людини значення (кб, Мб, Гб і т.д.). Параметру -h відповідає еквівалентна йому опція --human-readable|
| history | Відображає пронумеровану історію команд, де під №1 - найдавніше написана, а під останнім номером - остання написана команда (history) |
| history (№) | Відображає кількість останніх команд за заданим номером, включаючи команду history |
| !(№ команди) | Дозволяє виконати команду з історії за її номером в ній. |
| !-n | Виконує n-ну за рахунком команду з кінця, де n - порядковий номер команди з кінця в історії |
| ! ! | Виконує команду, що найчастіше використовуєтсья |
| ! (команда) | Виконує найчастіше використовуваний вид певної команди (якщо ми використовуємо найчастіше команду ls -l, то ввівши ! ls ми виконаємо команду ls -l) |
| (назва змінної)='(значення)' | Створює нову змінну або редагує існуючу, задаючи їй певне значення (можна і не числове). Приклад: NumOfFlows='3' |
| echo $(наз. змін.) | Відображає значення змінної. Може відображати як і локальну, так і глобальну змінну. Приклад: після виконання echo $NumOfFlows нам в наступному рядку видасть 3 |
| env | Виводить список всіх змінних та значення лише глобальних змінних |
| export (змінна) | Перетворює локальну змінну в глобальну |
| export (ком. створ. змін.) | Створює змінну одразу як глобальну |
| unset (змінна) | Видаляє змінну |
| type (команда) | Визначає тип команди / Яка це команда за псевдонімом / В деяких випадках показує шлях до заданої команди |
| which (команда) | Показує весь шлях до заданої команди |
| type -a (команда) | Показує тип команди та шлях до неї |
| alias | Показує всі "псевдоніми" для команд, що задані в оболонці |
| alias (псевд.)="(команда)" | Створює "псевдонім" для даної команди, який може використовуватися як задана команда |
| date | Виводить сьогоднішню дату та поточний час |
| man (команда) | Показує ім'я команди, описує призначення, як вона виконуєтсья, показує всі її опції, список пов'язаних файлів, автора, авторські права та деяку іншу інформацію (слово man йде від англ. Manual - посібник)|
| man -f | Використовується для пошуку посібників за назвою. whatis |
| man -k (ключ. слово) | Шукає збіги за ключовим словом в усіх посібниках. apropos |
| whatis | Виконує те, що й man -f |
| whereis | Виконує пошук команд чи файлів та виводить шлях, за яким їх в основному можна знайти. |
| locate | Виконує пошук команд чи файлів в базі даних з моменту її створення |
| locate -c | Показує скільки збігів при пошуку було виявлено (locate -c passwd) |
| locate -b | Виконує пошук команд чи посібників та показує лише збіги, що були виявлені в імені самих файлів чи команд |
| passwd | Використовується для зміни пароля |
| updatedb | Виконує оновлення бази даних |
| info | Показує документацію щодо заданої команди |
| (команда) --help | Дозволяє швидко ознайомитися з принципом та метою використання  |


Фукнції використовуються для створення нових команд або виконання кількох команд одразу. Вони задаються так:

*функція* () {

*команда№1*

*команда№2*

*команда№n*

}

> Деякі параметри можна комбінувати, тому тут показано не всі варіації команд.


# Контрольні запитання (Микитенко Назарій)
## Відповіді на контрольні запитання:
***1.*** There are two types of commands in the Bash shell: internal and external.
**Internal** — commands integrated into the shell, which are in the computer's RAM during operation.
**External** - stored as files in the system directory.

***2.*** Environment variables are dynamic named values ​​that affect the behavior of processes running on the computer. They also allow you to customize the program execution environment without changing their code. There are three types of environment variables: system environment variables, user variables, and local variables. 
System environment variables are loaded immediately when the operating system is started and stored in certain configuration files. System changes are the most important and are initiated by the operating system and applied to all users and processes. 
User variables are set by individual users and are valid only within their directories and session. 
Local variables are valid only within one current session. When it is completed, they will be permanently deleted and everything will have to be created manually to start again, and they are not saved in separate files.

***3.*** The *$PS1* variable selects the main Bash seed prompt string. This line is shown every time before the skin command. To see the current value of PS1, there is a command: *echo $PS1* .

***4.*** You can change the value of the *$PS1* variable by setting it to a new value with the export **PS1=" hihihaho@euu> "** command, which will change the appearance of the main prompt line in Bash. To make these changes permanent, add *~/.bash_profile* .

***5.*** The double quotes tell the shell to treat the text between the quotes ("...") as normal characters.

***6.*** Control instructions are used to interact with the operating system through the CLI. Types of instructions: file commands *(ls, mv)*, navigation commands *(cd)*, user management commands *(adduser, deluser)*, process management commands *(ps, kill)*, system commands *(shutdown, systemctl)*, network commands *(ssh, ping)*, package management commands *(apt)*.

***7.*** In Bash, the symbol at the end of the prompt line indicates the user's privileges, for example: 
**$** *is a regular user* and **#** *is a root user*.

***8.*** The *whereis* and *locate* commands are used to find files.
whereis is used to find the location of executable files, source code, and manual pages for a given command, and searches for these files in standard system directories such as */bin*, */sbin*, */usr/bin*, and others. Locate is used to quickly find files in the file system by name, and this command works on the basis of a pre-created database containing information about files and their locations, but this database must be regularly updated using the updatedb command.

# Висновок
During the laboratory work, the CLI mode of the Linux operating system was considered, as well as the features of CLI mode commands. As a result of the laboratory work 3, basic knowledge of CLI mode commands and basic terminal mode text commands used in various operating systems were mastered, as well as their description and features.

