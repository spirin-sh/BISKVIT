# Лабораторна робота №5

## Тема: “Знайомство з командами навігації по файловій системі та керування файлами та каталогами”

## Мета роботи:

1. Отримання практичних навиків роботи з командною оболонкою Bash.
   
2. Знайомство з базовими командами навігації по файловій системі.

3. Знайомство з базовими командами для керування файлами та каталогами.

## Завдання для попередньої підготовки (Микитенко Назарій)

### Словник базових англійських термінів:
|№|термін|переклад|
|---|------------------------------|-----------------------------------|
|1. |	Filesystem                   | файлова система                   |
|2. |	Directory                    | каталог                    |
|3. | Root directory               | кореневий каталог                 |
|4. |	Command Line Interface (CLI) | інтерфейс командного рядка        |
|5. |	Navigate                     | переміщатися |
|6. |	Permissions                  | права доступу                     |
|7. |	Move (mv)                    | перемістити або перейменувати     |
|8. |	Copy (cp)                    | копіювати                         |
|9. |	Remove (rm)                  | видалити                          |
|10.|	Hidden files                 | приховані файли                   |
|11.|	Home directory               | домашній каталог                  |
|12.|	Mount point                  | точка монтування                  |
|13.|	Wildcard (globbing)          | шаблон пошуку                     |

### Відповіді на питання

**2.1**. Windows has a tree-like file structure where each drive (C:, D:) is a separate file system. The main directory for the user is *C:\Users\Username\.*
In turn, in Linux, the entire file system is organized in the form of a single tree, starting from the root directory */.* Disks are mounted as subdirectories *(/mnt, /media).*

**2.2**. FHS (Filesystem Hierarchy Standard) is a standard that defines the location of system files and directories in Linux. It establishes uniform rules for different distributions, which ensures compatibility and predictability of the file system. For example, the command:

*/bin, /sbin* – executable files
*/etc* – configuration files
*/home* – user directories
*/var* – variable data (logs, cache)
*/tmp* – temporary files

**2.3.** Basic commands for working with files and directories in Linux.

2.3.1. Creation - *touch filename, mkdir dirname*

2.3.2. Move - *mv source destination*

2.3.3.	Copying - *cp source destination, cp -r dir1 dir2*

2.3.4.	Delete - *rm filename, rm -r dirname*


## Хід роботи (Клімчук Ярослав)

### Перелік команд з курсу Linux


| **Command**                  | **Explanation**                                                                                   |
|------------------------------|---------------------------------------------------------------------------------------------------|
| **Navigation and Listing**   |                                                                                                   |
| `ls`                         | Lists directory contents (Note: `ls` is not directly in the text but implied; use `dir` in some contexts). |
| `pwd`                        | Prints the current working directory (e.g., `/home/user`).                                       |
| `cd`                         | Changes the current directory (e.g., `cd /path` moves to specified path).                        |
| `cd Documents`               | Moves to the "Documents" directory in the current location.                                      |
| `cd Junk`                    | Moves to the "Junk" directory in the current location.                                           |
| `ls -a`                      | Lists all files, including hidden ones (starting with `.`).                                      |
| `ls -l`                      | Lists files in long format (details like permissions, owner, size).                              |
| `ls -d`                      | Lists directories themselves, not their contents (e.g., `ls -d /etc`).                          |
| `ls -ld`                     | Combines `-l` and `-d`: long format for directories only.                                        |
| `ls -R`                      | Lists recursively, showing contents of subdirectories.                                           |
| `ls -S`                      | Sorts files by size, largest first.                                                             |
| `ls -lrt`                    | Long format (`-l`), reverse order (`-r`), sorted by modification time (`-t`).                    |
| `ls -t`                      | Sorts files by modification time, newest first.                                                 |
| `ls -lrS`                    | Long format (`-l`), reverse order (`-r`), sorted by size (`-S`).                                |
| `ls -tl`                     | Sorts by time (`-t`), in long format (`-l`).                                                    |
| `ls -lSh`                    | Long format (`-l`), sorted by size (`-S`), with human-readable sizes (`-h`).                    |
| `ls -lS`                     | Long format (`-l`), sorted by size (`-S`).                                                      |
| **Globbing with `echo`**     |                                                                                                   |
| `echo /etc/t*`               | Displays files in `/etc/` starting with "t" (e.g., `timezone`).                                 |
| `echo /etc/*.d`              | Displays files in `/etc/` ending with ".d" (e.g., `apparmor.d`).                                |
| `echo /etc/r*.conf`          | Displays files in `/etc/` starting with "r" and ending with ".conf" (e.g., `resolv.conf`).      |
| `echo /etc/t???????`         | Displays files in `/etc/` starting with "t" and exactly 7 characters long (e.g., `termcap`).    |
| `echo /etc/*????????????????????` | Displays files in `/etc/` with 16+ characters (e.g., long filenames).                     |
| `echo /etc/*.???`            | Displays files in `/etc/` with a 3-character extension (e.g., `foo.bar`).                       |
| `echo /etc/[gu]*`            | Displays files in `/etc/` starting with "g" or "u" (e.g., `group`, `udev`).                     |
| `echo /etc/[a-d]*`           | Displays files in `/etc/` starting with "a" to "d" (e.g., `apt`, `bash.bashrc`).                |
| `echo /etc/*[9-0]*`          | Likely a typo; intended `[0-9]` matches files with digits (e.g., `rc0.d`). Reverse range invalid.|
| `echo /etc/*[0-9]*`          | Displays files in `/etc/` containing digits (e.g., `rc3.d`).                                    |
| `echo /etc/[!a-t]*`          | Displays files in `/etc/` not starting with "a" to "t" (e.g., `udev`, `xattr.conf`).            |
| **File Operations**          |                                                                                                   |
| `ls /etc/adduser.conf`       | Lists specific file `/etc/adduser.conf` (checks existence).                                     |
| `ls /etc/alternatives`       | Lists contents of `/etc/alternatives` directory.                                                |
| `ls /etc/x*`                 | Lists files in `/etc/` starting with "x" (e.g., `xattr.conf`).                                  |
| `cp /etc/hosts ~`            | Copies `/etc/hosts` to the user's home directory (`~`).                                         |
| `cp -v /etc/hosts ~`         | Copies `/etc/hosts` to `~` with verbose output (`-v`) showing the action.                       |
| `cp /etc/hosts ~/hosts.copy` | Copies `/etc/hosts` to `~/hosts.copy` (new filename).                                           |
| `cp /etc/hostname example.txt` | Copies `/etc/hostname` to `example.txt` in the current directory.                             |
| `cat example.txt`            | Displays the contents of `example.txt`.                                                         |
| `cp /etc/timezone example.txt` | Overwrites `example.txt` with contents of `/etc/timezone`.                                    |
| `ls -l example.txt`          | Lists `example.txt` in long format (shows details).                                             |
| `cp -i /etc/skel/.* ~`       | Copies hidden files from `/etc/skel/` to `~`, prompting before overwrite (`-i`).                |
| `cp -n /etc/skel/.* ~`       | Copies hidden files from `/etc/skel/` to `~`, no overwrite if files exist (`-n`).               |
| `cp -r source_directory destination_directory` | Copies `source_directory` and its contents to `destination_directory` recursively (`-r`). |
| `mv source destination`      | Moves or renames `source` to `destination`.                                                     |
| `ls -l sample`               | Lists `sample` in long format (checks details).                                                 |
| `rm sample`                  | Deletes the file `sample`.                                                              |
| `touch sample`               | Creates an empty file named `sample` (or updates its timestamp if it exists).                   |
| `rm Videos`                  | Attempts to delete `Videos` (fails if it’s a directory; use `rm -r Videos` for directories).    |

### 3. Робота в терміналі

![Image](https://github.com/user-attachments/assets/46775a21-c661-4d70-b01f-20723bad1c7f)

![Image](https://github.com/user-attachments/assets/2ad0c34e-d013-4791-aad3-8ea0e13554ad)

![Image](https://github.com/user-attachments/assets/0dab2426-e780-4035-a850-bd0005bd53d2)

![Image](https://github.com/user-attachments/assets/3a7d2688-9edd-44d8-818b-2e47b363e387)

![Image](https://github.com/user-attachments/assets/68e5442c-b6cc-48b8-a460-f002cf450b9b)

![Image](https://github.com/user-attachments/assets/5a0920da-6b39-40fc-83b4-43c2e122f818)

![Image](https://github.com/user-attachments/assets/18608dd1-8d4b-4f03-b2a4-2d40b1e5e02d)

![Image](https://github.com/user-attachments/assets/fda9345f-fe00-43b0-b02b-ba0fef49cab4)

### 4. Оптс команд


| **Command**   | **Where It Takes You**                  |
|---------------|----------------------------------------|
| `cd /`        | Moves to the root directory (/), the top-level directory of the file system.                  |
| `cd /home`    |  Moves to the /home directory, which typically contains user home directories.                   |
| `cd ~`        | Moves to the home directory of the current user (/home/username or another designated home path).                 |
| `cd`          | Equivalent to cd ~, moves to the user's home directory.               |
| `cd ..`       | Moves up one level in the directory hierarchy (to the parent directory).                     |
| `cd ../..`    | Moves up two levels in the directory hierarchy.                      |
| `cd -`        | Switches to the previous working directory.                     |




## Контрольні запитання (Краснопір Богдан)

### 1. Як можна переглянути шлях до домашньої директорії користувача за допомогою команди `echo`?

We can do it by using options ~ or $HOME

![alt text](https://i.imgur.com/x9uKrks.png)

### 2. Чи можна переглянути вміст кореневого каталогу, перебуваючи у домашньому каталозі користувача без переходу у кореневий каталог?

Так, це можливо зробити. Для цього необхідно використати команду `ls` з параметром /.

![alt text](https://i.imgur.com/mb5mJ7x.png)

### 3. Яким чином в терміналі можна додати інформацію в порожній файл?

You can add information to file by using `cat` or `echo`.

We use `cat` command like this: `cat > example.txt`. After execution we can add any information to our text file. When we done, press `Ctrl + D` to stop editing.

We use `echo` like this: `echo "example text" > example.txt`. In quoting marks we write down our text.

Символ `>` спрямовує вивід команд в файл, перезаписуючи його зміст.

### 4. Як скопіювати та видалити існуючий каталог? Чи буде відмінність в командах, якщо каталог буде не порожній при цьому.

To copy directory we use `cp -r` as  _cp -r source_directory destination_directory_. -r option allows `cp` command to copy both files and directories (without -r it'll give us an error message).

To delete directory we use `rm -r` command. By default `rm` does't delete directories, that's why we using -r. Also there is `rmdir` command, that only deletes directory when it's empty.

### 5. У якому з наведених нижче прикладів відбувається переміщення файлу? його перейменування? одночасно обидві дії?

`mv /work/tech/comp.png. /Desktop`   -  Виконується переміщення файлу.
`mv /work/tech/comp.png. /work/tech/my_car.png`  -  Виконується перейменування файлу.
`mv /work/tech/comp.png. /Desktop/computer.png`  -  Виконується переміщення та перейменування файлу.


## Висновок

During the laboratory work, the basic commands for working with the file system in Linux were considered, including directory navigation, file manipulation (copying, moving, deleting),
using wildcards (globbing) and performing operations through the terminal.
Various parameters of the *ls* command were studied to view files and their characteristics, as well as the *echo, cat, cp, mv, rm,* commands that allow you to work effectively with files and directories.
During the practical part, a set of test operations in the terminal was performed in accordance with the tasks and answers to control questions were completed.
