# Лабораторна робота №6

## Тема: “Команди Linux для архівування та стиснення даних. Робота з текстом”

## Мета роботи:
1. Отримання практичних навиків роботи з командною оболонкою Bash.
   
2. Знайомство з базовими командами для архівування та стиснення даних.
   
3. Знайомство з базовими діями при роботі з текстом у терміналі.
   

## Завдання для попередньої підготовки (Микитенко Назарій)

### Словник базових англійских слів
|Слово |Переклад |
|-|-|
|Compression | Стистення|
|Archive  |Архів|
|Directory | Каталог|
|File | Файл|
|Command | Команда|
|Parameter | Параметр|
|Outpu t| Виведення|
|Input | Введення|
|Standart output | Стандартне виведення|
|Stream | Потік|
|Filter | Фільтр|

### Відповіді на питання
**4.1**

|Команда|Призначення|Основні параметри|Встановлення|
|-|-|-|-|
|tar|Архівування файлів/каталогів в один файл, з можливістю стискання|-c (створити), -x (розпакувати), -v (вивід), -f (файл), -z (gzip), -j (bzip2), -J (xz)|Вже встановлено у більшості систем|
|gzip|Стискання файлів за алгоритмом DEFLATE, швидке стискання|-d (розпакувати), -r (рекурсивно), -l (статистика), -c (вивід в stdout), -1..-9 (якість)|sudo apt install gzip|
|bzip2|Стискання з високою якістю, але повільніше gzip, алгоритм Burrows-Wheeler|-d (розпакувати), -s (економія пам’яті), -1..-9 (розмір блоку)|sudo apt install bzip2|
|xz|Дуже висока якість стискання, повільне стискання, сучасний алгоритм LZMA2|-d (розпакувати), -l (статистика), -c (вивід), -0..-9 (якість), -e (екстремальне стискання)|sudo apt install xz-utils|
|zip|Стискання в популярний формат zip, сумісний із Windows|-r (рекурсивно), -e (шифрування), -9 (максимальне стискання)|sudo apt install zip|

**4.2**

*1*.	Архівування та стиснення gzip:

	*tar czvf archive.tar.gz myfolder/*
 
*3*.	Архівування та стиснення bzip2:

	*tar cjvf archive.tar.bz2 myfolder/*
 
*5*.	Архівування та стиснення xz:

	*tar cJvf archive.tar.xz myfolder/*
 

**4.3**

|Команда|Призначення|Основні параметри|
|-|-|-|
|cat|Виводить вміст файлів у термінал|-n (нумерація рядків), > (перенаправлення)|
|less|Перегляд файлів посторінково з прокруткою|-N (номери рядків), / (пошук)|
|more|Перегляд файлів посторінково (обмежений функціонал)|+n (від початку n-го рядка)|
|head|Вивід перших рядків файлу|-n N (N перших рядків)|
|tail|Вивід останніх рядків файлу|-n N (N останніх рядків), -f (режим стеження)|

**4.4**

**У Bash потоки даних поділяються на:**

*1.* stdin (0) – стандартне введення,

*2.* stdout (1) – стандартне виведення,

*3.* stderr (2) – стандартне виведення помилок.

У Каналах:

Команда cmd1 | cmd2 передає вивід cmd1 на вхід cmd2. Наприклад: cat file.txt | grep "word"

**Перенаправлення потоків:**

	> – перенаправлення stdout у файл
 
	>> – додавання stdout до файлу
 
	2> – перенаправлення stderr у файл
 
	&> – перенаправлення stdout та stderr у файл

	/dev/null – спеціальний файл, що "гасить" вивід
 

**4.5**

Команда *grep*   використовується для пошуку рядків у файлі чи потоці, що відповідають заданому шаблону або регулярному виразу, у файлах або виводі інших команд. Вона дозволяє швидко знаходити потрібну інформацію в тексті.
Наприклад: *grep "error" logfile.txt*

## Хід роботи (Краснопір Богдан)

### Таблиця-опис команд

|Команда|Опис|
|-|-|
|mkdir mybackups|Створення нової директорії mybackups у домашньому каталозі користувача|
|tar -cvf mybackups/udev.tar /etc/udev|Команда tar використовується для об’єднання кількох файлів в один файл. В даному випадку вміст директорії  /etc/udev  буде збережено в архів udev.tar у директорії mybackups. Параметр -c повідомляє команді tar створити файл tar. Параметр -v означає "verbose", який наказує команді tar продемонструвати, що вона робить. Параметр -f використовується для вказівки назви файлу tar|
|gzip 'назва файлу'|Виконує стиснення поточного файлу, змінюючи його формат на .gz, використовує алгоритм стиснення Lempel-Ziv|
|gzip -l 'назва файлу'|Виводить інформацію про стиснення поточного файлу|
|gunzip 'назва стиснутого файлу'|Декомпресує файл, тобто повертає його до первинного стану|
|gzip -d|Те саме, що й `gunzip`|
|bzip|Виконує стиснення за алгоритмом "Burrows-Wheeler block sorting", змінює формат на .bz|
|bunzip|Декомпресує файлм формату .bz|
|xz|Виконує стиснення за алгоритмом "Lempel-Ziv-Markov (LZMA)", змінює формат на .xz|
|unxz|Декомпресує файлм формату .xz|
|tar -c [-f ARCHIVE] [OPTIONS] [FILE...]|Створення архіву. Замість ARCHIVE може бути будь-яка назва для архіву. Замість FILE повинна бути назва файлу чи файлів, які будуть заархівовані|
|tar -cf alpha_files.tar alpha*|Приклад минулої команди. Всі файли, що починаються на alpha будуть включені до архіву alpha_files.tar|
|tar -czf alpha_files.tar.gz alpha*|З параметром -z виконує стиснення архіву за допомогою команди gzip|
|tar -cjf folders.tbz School|Разом з параметром -j виконує стиснення за допомогою команди bzip2|
|tar -tjf folders.tbz|Параметр -t використовується для виведення списку файлів в архіві, а -j в даному випадку декомпресує файли за допомгою команди bunzip2|
|tar -xjf folders.tbz|Параметр -x використовується для розархівування файлів|
|tar -xjvf folders.tbz|Параметр -v виводить почергово виводить на екран файли, що розархівовуються|
|tar -xjvf folders.tbz School/Art/linux.txt|Додаючи в кінці назву файлу (School/Art/linux.txt), лише цей файл буде розархівований|
|zip alpha_files.zip alpha*|Архівує файли в формат .zip. Також після виконання показує на скільки файли були стиснуті у %|
|zip -r School.zip School|Те ж, що й попередня команда, але з рекусрією|
|unzip -l School.zip|Виводить список файлів в архіві|
|unzip School.zip|Виконує розархівування файлів, до кожного файлу дає певно опцію розархівування. Файли розархівовуються в поточний каталог, тому щоб уникнути незручностей з опціями можна скопіювати архів в новий каталог та розархівувати його там|
|unzip School.zip School/Math/numbers.txt|Розархівовує файл, який прописаний в кінці|
|cat food.txt|Виводить вміст текстового файлу food.txt|
|less|Виводить зміст файлу посторінково з можливістю переміщення по змісту. |
|more|Виводить зміст файлу посторінково з можливістю переміщення лише вперед|
|head /etc/sysctl.conf|Виводить 10 перших рядків з файлу|
|tail -5 /etc/sysctl.conf|Виводить останні 5 рядків з файлу|
|head -n 3 /etc/sysctl.conf|Виводить перші 3 рядки|
|tail -n +25|Відображає вміст файлу з 25-го рядка і до кінця|
|nl|Номерує те, що виводить команда, на приклад, ls|
|sort mypasswd|Сортує зміст файлу mypasswd за алфавітним порядком|
|sort -t: -n -k3 mypasswd|Сортує зміст файлу. -t відповідає за розмежування, -k відповідає на номер поля сортування (в нашому випадку це третє, бо -k3), -n відповідає за тип сортування|
|wc /etc/passwd /etc/passwd-|Виводить статистику файлу: к-сть байт, слів, рядків та назву файлу|
|cut -d: -f1,5-7 mypasswd|Виводить колонки з файлу. -d відповідає за розділення виведених даних за допомогою табуляції, -f визначає які поля виводити|
|grep --color bash /etc/passwd|Фільтрує вмість файлу та виводить його чи результат іншої команди. Параметр --color відповідає за підсвічення результатів сортування (в нашому випадку будуть підсвічуватись всі слова bash у виводі)|
|grep -c bash /etc/passwd|Виводить кількість підходящих рядків|
|grep -n bash /etc/passwd |Виводить колонки з файлу та підписує їх номер в файлі|
|grep -v nologin /etc/passwd|За допомогою -v виведе всі рядки, що не включають слово (в нашому випадку nologin)|
|grep '....' red.txt|Виведе всі слова, що містять 4 символи з текстового файлу ( . відповідає за 1 символ)|
|grep '[^0-9]' profile.txt|Виведе всі рядки, що включають числа 0-9 і підсвітить всі символи, крім чисел|
|grep 're*d' red.txt|Виведе рядки, в яких слово починається на re і закінчується на d (* відповідає за кількість символів від 0 до нескінченності)|
|grep '^root' /etc/passwd|Виведе рядки, які починаються словом root|
|grep 'r$' alpha-first.txt|Виведе рядки, які закінчуються буквою r|
|grep 're\*' newhome.txt|Виведе рядки, в яких є саме частинка re|
|grep -E 'e+' red.txt|Виведе рядки, в яких є один та більше символів е|
|grep -E 'gray|grey' spelling.txt|Виведе рядки, в яких є слова gray або grey|

### Робота з командою tar

Створення файлів .tar з одним та декількома файлами:

![image](https://github.com/user-attachments/assets/2c4cb05b-c90d-4e4e-a65e-4d3fc4e93286)

![image](https://github.com/user-attachments/assets/a55b8195-701f-4f5c-8f63-61472f6a8e43)

Перегляд вмісту файлу:

![image](https://github.com/user-attachments/assets/dfff582d-5611-4d13-9dbf-751deca6be6c)

Витягування вмісту архіву:

![image](https://github.com/user-attachments/assets/0832b31c-26b4-4762-a42a-a3aad15214c6)

Створення стиснутого архіву .tar.gz

![image](https://github.com/user-attachments/assets/12dad1ef-8d3f-4f3f-90dd-a5fe0f25272e)

Витягування вмісту:

![image](https://github.com/user-attachments/assets/9114751e-0d07-47cd-a137-fcfeee311e27)

Створення стиснутого архіву .tar.bz:

![image](https://github.com/user-attachments/assets/499a1c49-69a6-411d-8159-a7cd9ff3e6f1)

Витягування вмісту:

![image](https://github.com/user-attachments/assets/b007c01c-d073-4573-aa0b-fedb20e947f7)

### Перенаправлення потоків в bash:

**cmd 1> file** - результат команди STDUOT перенаправиться в файлі перезапише його

**cmd > file** - результат команди перенаправиться в файл і перезапише його

**cmd 2> file** - результат команди STDERR перенаправиться в файлі перезапише його

**cmd >> file** - результат результат команди перенаправиться в файл і запише його після наявної інформації

**cmd &> file** - результат всіх команд перенаправиться в файл і перезапише його

**cmd > file 2>&1** - виконає ту саму дію, що й попередня команда

**cmd >> file 2>&1** - виконає ту саму дію, що й попередня команда але не пререзаписує файл

**cmd 2>&1 > /dev/null** - перенапрявляє STDERR до STDUOT, але STDOUT перезаписує файл за шляхом

**cmd 2> /dev/null** - перенаправляє STDERR за шляхом та перезаписує файл

**cmd1 | cmd2** - передає результат команди 1 до команди 2

**cmd1 2>&1 | cmd2** - перенаправляє STDERR в STDUOT команди 1, і результат в свою чергу до команди 2

### Приклади перенаправлення

|Команда (контейнер команд)|Що виконує команда?|Який потік перенаправлення?|
|-|-|-|
|$echo "It is a new story." > story|Створить файл story з повідомленням It is a new story. Якщо ж файл існує, він перезапишеться|STDOUT команди `echo` в директорію story|
|$ date > date.txt|Перезапише файл date.txt результатом команди `date`|STDOUT команди `date` в файл date.txt|
|$ cat file1 file2 file3 > bigfile|Скопіює вміст file1, file2 та file3 до поточної директорії та створить bigfile.txt. Якщо файл існує, він перезапишеться|STDOUT команди `cat` з файлів 1,2,3 в файл bigfile|
|$ls -l >> directory|Створить новий файл з назвою directory та заповнить його результатом команди `ls -l`. Якщо ж файл існує, то вивід команди доповнить вже наявну інформацію|STDOUT команди `ls -l` до файлу directory|
|$ sort < file1_unsorted > file2_sorted|Введе дані з file1_unsorted до команди `sort`, яка в свою чергу перезапише file2_sorted|STDIN від file1_unsorted до команди `sort`, STDOUT від sort до file2_sorted|
|$ find -name '*.txt' > file.txt 2> /dev/nul|Якщо команда спрацювала, її результат перезаписує file.txt, але вразі помилки її результат перезаписується за директорією /dev/nul|STDOUT від команди до file.txt, STDERR від команди до директорії /dev/nul|
|$ cat file1_unsorted *pipe* sort > file2_sorted|Передає результат `cat file1_unsorted` до `sort`, а той в свою чергу перезаписує file2_sorted|STDOUT або STDERR від `cat file1_unsorted` до `sort`, STDOUT від `sort` до file2_sorted|
|$ cat myfile *pipe* grep student *pipe* wc -l|Результат `cat myfile` передається до `grep student`, результат якого в свою чергу передається до `wc -l`|STDOUT або STDERR від `cat myfile` до `grep student`, STDOUT або STDERR від `grep student` до `wc -l`, |

Знак конвеєра довелося замінити словом *pipe*, бо цей | символ відповідає за створення нових колокок в таблиці в .md файлі.

## Відповіді на контрольні запитання(Клімчук Ярослав)

### 1. Надайте порівняльну характеристику процесам стискання та архівування.

| **Feature**        | **Compression**                                              | **Archiving**                                                        |
|--------------------|---------------------------------------------------------------|----------------------------------------------------------------------|
| **Purpose**        | Reducing file size by removing redundancy.                    | Combining multiple files/directories into a single container.        |
| **Result**         | A smaller, compressed file.                                   | An archive file that includes multiple files or directories.         |
| **Algorithms**     | Utilizes compression algorithms (Deflate, LZMA, Zstd, etc.).  | May not compress (e.g., `tar`), but packages files together.        |
| **Common Usage**   | Works on single files or archive containers.                  | Handles multiple files and directories, maintaining their structure. |
| **Examples**       | `gzip`, `bzip2`, `xz`, `zstd`.                               | `tar`, `cpio`, `ar`. Often combined with compression (`tar.gz`).    |

---

### 2. Які програми, окрім наведених в роботі, можуть використовуватись для стискання та архівування файлів та каталогів в ОС Linux? Наведіть приклади та їх короткий опис.


-  7zip
  
   7-Zip is a free and open-source file archiver, a utility used to place groups of files within compressed containers known as "archives". Most of the 7-Zip source code is under the LGPL-2.1-or-later license; the unRAR code, however, is under the LGPL-2.1-or-later license with an "unRAR restriction", which states that developers are not permitted to use the code to reverse-engineer the RAR compression algorithm.
  - -Zip port for Linux.
  - **Algorithms**: LZMA / LZMA2.
  - **Formats Supported**: 7z, zip, tar, rar, and others.
  - **Features**: High compression ratio, AES-256 encryption.

---

-  lrzip (Long Range ZIP)
  
  lzip is a free, command-line tool for the compression of data; it employs the Lempel–Ziv–Markov chain algorithm (LZMA) with a user interface that is familiar to users of usual Unix compression tools, such as gzip and bzip2.

Like gzip and bzip2, concatenation is supported to compress multiple files, but the convention is to bundle a file that is an archive itself, such as those created by the tar or cpio Unix programs. Lzip can split the output for the creation of multivolume archives.

The file that is produced by lzip is usually given .lz as its filename extension, and the data is described by the media type application/lzip.
  - Optimized for compressing large files.
  - **Algorithms**: LZMA, Bzip2, ZPAQ.
  - **Features**: Excellent compression for large files using hybrid algorithms.


---

### 3. Порівняйте алгоритми стискання, що використовуються в командах (програмах), використовуваних в Linux. Які з алгоритмів можна вважати найшвидшим та найефективнішим?


| **Algorithm**  | **Tools/Commands** | **Compression Speed** | **Compression Ratio** | **Notes**                                       |
|----------------|--------------------|-----------------------|-----------------------|-------------------------------------------------|
| **gzip** (Deflate) | `gzip`, `gunzip` | High                 | Medium                | Fast, widely supported.                        |
| **bzip2**      | `bzip2`, `bunzip2` | Slower than gzip     | Better than gzip      | Supports multiple compression levels.          |
| **xz** (LZMA2) | `xz`, `unxz`       | Slow                 | Very High             | High efficiency, higher memory usage.          |
| **zstd**       | `zstd`, `unzstd`   | Very High            | Flexible (configurable) | Excellent trade-off between speed and ratio.   |
| **LZO / LZ4**  | `lzop`, `lz4`      | Extremely High       | Below Average         | Ultra-fast, ideal for real-time compression.    |

- **Fastest algorithms**: LZ4, Zstd.
- **Most efficient algorithms**: xz, lrzip.

---

### 4. Опишіть програмні засоби для стискання та архівування, що можуть бути використані у вашому мобільному телефоні.



 Android
- **ZArchiver**
  - Supports: zip, rar, 7z, tar, gzip, bzip2, etc.
  - Features: Archive creation, extraction, encryption, content preview.

- **RAR for Android**
  - From the makers of WinRAR.
  - Supports: RAR, ZIP, 7z, TAR, GZ.
  - Features: Repair corrupted archives, encryption.

- **B1 Archiver**
  - Supports 30+ archive formats.
  - Features: Password-protected archives, file preview without extraction.

---

### 5. Опишіть та порівняйте програмні засоби для стискання та (де)архівування даних у ОС сімейства Windows.

- WinRAR
Supports RAR, ZIP, 7z and other formats.
AES-256 encryption, the ability to split archives into parts.
Interface: graphical and console.

- 7-Zip
Free, open source.
Proprietary 7z (LZMA2) format, supports zip, rar, tar, gzip, iso, etc.
High compression efficiency.

- WinZip
Supports zip, rar, 7z, tar and other formats.
Commercial product, integration with cloud services, encryption.


| **Program**  | **Formats Supported**   | **Algorithm**  | **Features**                                              |
|--------------|-------------------------|----------------|-----------------------------------------------------------|
| **7-Zip**    | 7z, zip, tar, rar, etc. | LZMA2          | Open-source, high compression efficiency.                 |
| **WinRAR**   | rar, zip, 7z, etc.      | Proprietary    | Large archive support, multi-volume, AES encryption.      |
| **WinZip**   | zip, rar, 7z, tar, etc. | Proprietary    | Cloud integration, encryption, and a user-friendly GUI.   |

---

### 6. Поясніть яким чином стиснення та архівування даних може бути використано для резервування даних. В яких ще задачах системного адміністрування воно може бути використано.

**Data Backup**: Compression reduces storage needs and speeds up transfers by packing files into smaller archives (e.g., .tar.gz). Archiving simplifies management by bundling files into single units.

Other Sysadmin Uses:

- Log rotation

- Data sharing

- Software distribution (smaller installers/updates)

- Data migration 

- System migration

- Database/VM backups 

- Compliance 

- Disk space optimization
---

### 7. Яке призначення директорії файлу /dev/null?


In Unix-like systems, /dev/null is a special file that discards any data written to it and returns nothing when read. It’s used to suppress output (e.g., echo "text" > /dev/null), silence errors (e.g., ls /nonexistent 2> /dev/null), or provide empty input (e.g., cat /dev/null > file.txt). Essentially, it’s a "black hole" for data.
