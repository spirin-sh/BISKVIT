## Завдання для попередньої підготовки (Микитенко Назарій)


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
