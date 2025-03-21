## 2. Визначте який менеджер пакетів використовує ваш дистрибутив Linux. Опишіть основні команди для роботи з ним. (Краснопір Богдан)

  Curently i'm using Kali Linux. It is Debian based distro, so it have APT package manager, like Ubuntu or other.

  The basic comands to work with APT:

  1. sudo apt install _назва пакету_ - виконує встановлення нового пакету в систему.
  2. sudo apt install _назва пакету1_ _назва пакету2_ _назва пакету n_ - виконує встановлення одразу декількох пакетів за виконання одної команди. Пакети встановлюються почергово.
  3. sudo apt install ./_назва файлу_ - виконує встановлення файлу за його назвою.
  4. sudo apt install _назва пакету_=_версія пакету_ - виконує встановлення певної версії пакету.
  5. sudo apt remove _назва пакету_ - видаляє пакет. Так само, як і команди для встановлення, можна одразу видалити декілька пакетів.
  6. sudo apt autoremove - видаляє всі непотрібні пакети автоматично.
  7. sudo apt purge _назва пакету_ - видаляє пакет разом з файлами конфігурації. Також можливо видалити таким чином одразу декілька пакетів.
  8. sudo apt update - оновлює всі пакети в системі, змінюючи їх.
  9. sudo apt list --upgradable - виводить список пакетів, що можна оновити.
  10. sudo apt upgrade - оновлює пакети, заміняючи їх на нові. В кінці можна дописати назву пакету для оновлення лише того пакету.
  11. sudo apt dist-upgrade - оновлює пакети, що не можуть бути оновлені через оновлення інших пакетів, адже вони можуть повпливати на роботу цих програм.
  12. sudo apt list - виводить список всіх доступних пакетів для встановлення.
  13. sudo apt list --installed - виводить список всіх встановлених пакетів.
  14. sudo apt -qq list _назва пакету_ - показує, чи пакет встановлений в системі.
  15. sudo apt policy _назва пакету_ - показує версію пакету та з якого репозиторію він був встановлений.
  16. sudo apt search _назва пакету_ - шукає пакет в репозиторії.
  17. sudo apt show _назва пакету_ - виводить повну інформацію про пакет.
  18. sudo apt help - виводить основну інформацію про роботу з командою.

  To add a new repository, you need to add gpg-key firstly. After adding, you can run these comands to work with repository:

  - sudo apt-add-repository '_посилання на репозиторій_' - додає новий репозиторій до директорії.
  - sudo apt-add-repository --remove '_посилання на репозиторій_' - видаляє репозиторій.
  - sudo apt autoclean - очищує систему та видаляє непотрібні пакети разом з непотрібними репозиторіями.

## 3. Встановіть у терміналі через менеджер пакетів на свою систему. (Краснопір Богдан)
  
  I've installed the VLC media player as an example.

#### Instalation of VLC:

  First we enter `sudo apt install vlc`. After we are confirming instalation by typing "y"
  
![image](https://github.com/user-attachments/assets/2202eb2c-dbcc-4fc8-ad85-eaaa4c30d7df)

  After instalation, we can find VLC player in our App Manager:
  
![image](https://github.com/user-attachments/assets/e1b0b0ef-8229-409a-8338-2ff51a55f4a7)

  To test if player works correctly, i've opened sound file with .flac format and it's playing it without problem:

![image](https://github.com/user-attachments/assets/b52c264e-f434-43c1-999d-7b929dad65af)

#### Instalation of IDE for programing language have the same proces, as before. The only diference is that your program may not be founded in standard repository, so you'll need to add a new one, that contains needed program. Process of instalation also can be simplyfied by using a software store.
