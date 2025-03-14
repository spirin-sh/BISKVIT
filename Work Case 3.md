## 3. Розгортання мережі між віртуальними машинами.

Я використовував дві віртуальні машини Kali Linux

### Основні команди для налаштування мережевих параметрів ОС.

|Команда|ЇЇ призначення|
|-|-|
|ip a|Показує ip-адреси підключених пристроїв|
|nmcli connection show|Показує всі підключення, а саме: назву підключення, UUID, тип підключення та пристрій|
|sudo nmtui|Запускає графічний інтерфейс, через який можна здійснювати просте керування підключеннями: активувати чи деактивувати підключення, додати нове чи редагувати існуюче, задати ім'я хоста чи відключити радіопідключення|
|sudo ip route add default via 192.168.1.1|Команда задає шлюз за замовчуванням (ip-адреса може відрізнятися)|
|sudo dhclient eth0|Надсилає запит з метою отримання ip-адреси через DHCP (eth0 - пристрій, до якого ми підключені)|
|sudo ip addr add 192.168.1.100/24 dev eth0|Встановлює статичну ip-адресу|

#### Команд насправді більше, але ці є основними.

### Демонстрація того, що обидві ОС мають вихід у мережу Інтернет

Це виконано за допомогою програшу відео на ютубі.

![alt text](https://i.imgur.com/WSuK8DG.png)

### Обмін повідомленнями між двома ОС

В першу чергу необхідно створити мережу між ними. Також необхідно буде ввімкнути DHCP, адже у двох ОС однакова IP-адреса (10.0.2.15)

![alt text](https://i.imgur.com/fDYFTZf.png)

#### Створення мережі:

1. Enter to the Network Mannager.

   ![alt text](https://i.imgur.com/I6y2Xf9.png)

2. You will see the Network Mannager window. Press create to create new NAT network. After you need to set it's name, IPv4 prefix and turn on DHCP. Resul will be like this:

   ![alt text](https://i.imgur.com/tQs9fc4.png)

3. Now you need to change your VM connection to our NAT network. To do it you need to enter VM Settings -> Network. Now you'll change connection to "NAT network" and chose name of our network.

   ![alt text](https://i.imgur.com/3S1F5gU.png)

4. To show our VM IP-addresses i've usef `ip a` command

   ![alt text](https://i.imgur.com/fDYFTZf.png)

   We can see that our VMs have same IP. So i've changed one of two:

   ![alt text](https://i.imgur.com/ih6dQtF.png)

5. Now let's ping our VMs

   ![alt text](https://i.imgur.com/FopOGEL.png)

  We can see that they both recieved and answered to ping's.

### Налаштування мережевої папки

  Firstly, you need to create one on your host PC. I've added the text file to check if it's working.

  Now we are adding folder to our VMs. At this point VMs must be started. To do it you need to enter VM settings and enter "Shared folders". There we can add new folders or check existent.

  ![alt text](https://i.imgur.com/bZsYcsq.png)

  Now press "Додати" button to add a new shared folder. You need to add same directory as your shared folder has.

  ![alt text](https://i.imgur.com/K7Ln5zH.png)

  After adding it, we can see in our file mannager it's appear.

  ![alt text](https://i.imgur.com/YRwr9QK.png)

  Also it asks us for a permissions, so all of next actions that i've done were made in superuser mode.

  ![alt text](https://i.imgur.com/HD4I0Xr.png)

  If we check the content of folder we'll see our text file with same symbols.

  File in host:
  
  ![alt text](https://i.imgur.com/JqLqKVZ.png)

  File in VM:
  
  ![alt text](https://i.imgur.com/4NwFzER.png)

  Now we can copy this text file to Desktop folder and home directory:

  Copy to desktop:
  
  ![alt text](https://i.imgur.com/hukLBz4.png)

  Copy to /home:

  ![alt text](https://i.imgur.com/rvBxoJo.png)

  ![alt text](https://i.imgur.com/yxXeW3F.png)
