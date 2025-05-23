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
