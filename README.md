# NetPractice

## Цель данного проекта научиться  настривать межсетевые подключения между компьютерами.

<details>
<summary>Описание</summary>
 
[subject](https://github.com/luta-wolf/NetPractice/blob/master/subject/en.subject.pdf)

Вам придется настроить небольшие сети. Для этого необходимо будет понять, как работает TCP/IP-адресация.
Вам нужно будет пройти 10 уровней (т.е. 10 упражнений) и включить их в свой Git репозиторий.

Сначала загрузите файл (`net_practice.tgz`), прикрепленный к странице проекта.
Затем извлеките файлы в любую нужную папку.
В этой папке запустите index.html файл.
Этот интерфейс должен открыться в вашем веб-браузере:

<img width="748" alt="image" src="https://user-images.githubusercontent.com/58044383/173697470-c82283ad-f385-4df5-a486-be94ff4ebccd.png">

 - Вы можете попрактиковаться, если введете свой логин в поле
 - Или вы можете попробовать версию "экзамен", если оставите поле пустым.

Для обучения доступно 10 уровней.Для каждого уровня появляется нефункционирующая сетевая диаграмма.
В верхней части окна вы увидите цель, которую нужно достичь: проблемы, которые нужно решить,
чтобы сеть работала нормально. Есть две кнопки, которые вы можете использовать:
• "Проверьте еще раз", чтобы убедиться, что ваша конфигурация была правильной или нет.
• "Получите мою конфигурацию", чтобы загрузить вашу конфигурацию для отправки в гит репозиторий.

<img width="900" alt="image" src="https://user-images.githubusercontent.com/58044383/173689800-cb9f0382-5a0f-4182-845e-2efae1483bfb.png">


  Когда вы успешно пройдете уровень, появится новая кнопка. Нажмите на нее чтобы перейти на следующий уровень.


<img width="822" alt="image" src="https://user-images.githubusercontent.com/58044383/173690126-a4fd5b1a-5fae-447f-a5fe-810bb175a29f.png">

В нижней части страницы вы увидите журналы. Они могут быть полезны, чтобы понять, почему ваша конфигурация неверна.

<img width="231" alt="image" src="https://user-images.githubusercontent.com/58044383/173690468-26686072-eefc-4e06-8525-f0e0b328686b.png">

Чтобы добиться успеха, измените незатененные поля до тех пор, пока конфигурация сети не будет правильной.
Чтобы выполнить это задание, настоятельно рекомендуется понять, как работает адресация в сети,
в которой есть такие устройства, как маршрутизаторы. Читайте о TCP /IP -адресации.

### Защита
- Во время защиты вам нужно будет пройти 3 случайных уровня, как указано на тренинг-платформа за 15 минут.
- Вам не разрешается использовать внешние инструменты во время оценки. (Использование простого калькулятора допустимо).
</details>

<details>
<summary>Терминология</summary>
 
### Таблица маршрутизации
 Синее окно - таблица маршрутизации - правила, по которым определяется лучший путь для передачи пакетов.
 Это электронная база данных в маршрутизаторе, которая представляет из себя некий набор правил. В ней содержится информация о сетевых маршрутах по которым определяется наилучший путь для передачи пакета данных. Она содержит в себе адрес и маску сети подключения, адрес шлюза (т. е. маршрутизатора сети, на который отправляются данные), метрику (расстояние) и интерфейс (имя и индентификатор устройства).
 <img width="962" alt="image" src="https://user-images.githubusercontent.com/58044383/174404596-36f3809d-a2ba-4c00-95bc-296f8914fba0.png">
 
 + `Слева` адрес и маска сети назначения (куда хотим отправить пакет).
 + `Справа` адрес шлюза (адрес роутера, куда направится пакет сразу).
 + В таблице маршрутизации `default` или `0.0.0.0/0` соответствуют всему

### Коммутатор (switch)
Это устройство для соединения нескольких устройств в одной сети. У всех устройств одинаковая маска.

### Роутер (маршрутизатор)
Это сетевой компьютер, который обрабатывает полученные данные по заданным правилам администратора и опираясь на таблицу маршрутизации определяет путь для пересылки данных.
 
 <img width="858" alt="image" src="https://user-images.githubusercontent.com/58044383/174405741-cc0b1ab9-a3a5-4dd6-b279-64419b1dcb23.png">
 
### Перед выполнением заданий помним:
+ Первый IP-адрес подсети - _адрес сети_
+ Последний IP-адрес подсети - _широковещательный_.
+ IP-адреса соседних сетей не должны перекрываться.
+ IP-адреса `10.0.0.0 - 10.255.255.255`, `172.16.0.0 - 172.31.255.255` и  `192.168.0.0 - 192.168.255.255` 
зарезервированы для частных адресов, не могут соединяться с интернетом.
+ IP-адреса `127.0.0.1-127.255.255.254` циклический IP, используется для установления соединения с самим собой.
+ У роутера для каждой подсети своя маска.
+ Адрес сети начинается с 0 или четной цифры.

### Примеры
IP-адрес `200.200.200.200/24`
+  `200.200.200.`0 - адрес сети
+  200.200.200.`255` - широковещательный адрес
+  200.200.200.`200` - адрес компьютера
+  `/24` - маска подсети на 254 компьютера (256 - 2 = 254)
+ 200.200.200.1 - 200.200.200.254 - диапазон адресов
 
IP-адрес `196.32.12.254/30`
 + `196.32.12.252`   - адрес сети
 + 196.32.12.`255` - широковещательный адрес
 + 196.32.12.`254`  - адрес компьютера
 + `/30` - маска подсети на 2 компьютера (4 - 2 = 2)
 + 196.32.12.253 - 196.32.12.254 - диапазон адресов
</details>



<details>
<summary>Полезные материалы</summary>
 
+ Почитать подробнее можно [здесь](https://github.com/evgenkarlson/ALL_SCHOOL_42/blob/master/00_Projects__(%D0%9E%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D0%BE%D0%B5_%D0%9E%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5)/00_Global_(begin_cadet)/02____netwhat/answers_to_netwhat.md).
+ Таблица соответствия [масок подсетей](https://www.gotoadm.ru/table-subnet-masks/).
+ IP [калькулятор](https://ip-calculator.ru/#!ip=192.168.114.253/30).
+ Лекция по [маршрутизации](https://www.youtube.com/watch?v=kZqqk1tixfk&ab_channel=AndreySozykin).
+ Лекция по [TCP/IP](https://www.youtube.com/watch?v=rLUzYeLdM0k&ab_channel=HillelITSchool).
+ Подробный курс лекций по [компьютерным сетям](https://www.youtube.com/watch?v=OLFA0soYGhw&list=PLtPJ9lKvJ4oiNMvYbOzCmWy6cRzYAh9B1&ab_channel=AndreySozykin).
 
P.S. При составлении материала пользовался работами [Sglossu](https://github.com/Sglossu/NetPractice), [divinepet](https://divinepet.github.io/NetPractice/) и [F@nzil](https://github.com/ifanzilka/NetPractice)
</details>

<details>
<summary>Level 1</summary>
<img width="978" alt="image" src="https://user-images.githubusercontent.com/58044383/174407429-69ecba41-db3a-429e-8724-84ee35ce3ee7.png">
 или
 <img width="1401" alt="image" src="https://user-images.githubusercontent.com/58044383/174454794-982d626d-7c8e-4739-ac11-8fe0bad20196.png">
</details>
<details>
<summary>Level 2</summary>
<img width="982" alt="image" src="https://user-images.githubusercontent.com/58044383/174407448-e31f8481-cfd9-4111-b25d-c552c1aff4c4.png">
 или
 <img width="1322" alt="image" src="https://user-images.githubusercontent.com/58044383/174454831-bc71131b-2c99-4496-996d-e2324111772b.png">
</details>
<details>
<summary>Level 3</summary>
<img width="982" alt="image" src="https://user-images.githubusercontent.com/58044383/174407487-af6354f0-a053-430d-8160-6ccfcadcf554.png">
 или
 <img width="1171" alt="image" src="https://user-images.githubusercontent.com/58044383/174454872-ce1a0d07-327a-4bf4-b700-d6180e007289.png">
</details>
<details>
<summary>Level 4</summary>
<img width="979" alt="image" src="https://user-images.githubusercontent.com/58044383/174407508-11d03209-1e58-43cf-87d5-ed7160eacb1c.png">
 или
 <img width="1247" alt="image" src="https://user-images.githubusercontent.com/58044383/174454889-483c1419-688d-48a3-b113-88e7bb2a89b4.png">
</details>
<details>
<summary>Level 5</summary>
<img width="982" alt="image" src="https://user-images.githubusercontent.com/58044383/174407545-f132674e-1499-4424-99d4-50ac18532e67.png">
 или
 <img width="1202" alt="image" src="https://user-images.githubusercontent.com/58044383/174454905-952df831-eb9a-47ba-b6db-a16bdadd3b70.png">
</details>
<details>
<summary>Level 6</summary>
<img width="978" alt="image" src="https://user-images.githubusercontent.com/58044383/174407570-1da7239d-5f23-48a5-b02a-ae5b28a96333.png">
 или
 <img width="1329" alt="image" src="https://user-images.githubusercontent.com/58044383/174454922-e4a535da-6da4-4aec-84e6-3a9bc7ef3b83.png">
</details>
<details>
<summary>Level 7</summary>
<img width="979" alt="image" src="https://user-images.githubusercontent.com/58044383/174407637-5337c20a-619e-4411-92f2-2f0497e31d69.png">
 или
 <img width="1330" alt="image" src="https://user-images.githubusercontent.com/58044383/174454963-2a5b637e-c00c-44d3-be13-e5d88307c8ff.png">
</details>
<details>
<summary>Level 8</summary>
<img width="981" alt="image" src="https://user-images.githubusercontent.com/58044383/174407713-07d0e666-fd2d-4a5b-8296-143c88487e00.png">
 или
 <img width="1331" alt="image" src="https://user-images.githubusercontent.com/58044383/174454978-476453a2-c3ef-45c1-8e42-768fe3316386.png">

</details>
<details>
<summary>Level 9</summary>
 Эту задачу можно решить тремя способами.
 Первый:
 
<img width="980" alt="image" src="https://user-images.githubusercontent.com/58044383/174407778-29e9091b-5bd0-430b-8aa2-135f768de78b.png">
Второй:
 <img width="1101" alt="image" src="https://user-images.githubusercontent.com/58044383/174408963-fc373b70-b5e7-4162-8eff-602166a300d1.png">
 
В поле `internet` изменили маску с `/0`на `/24` и указали обе сети `22.22.22.0 и 77.77.77.0`.
Третий:
 
 <img width="1100" alt="image" src="https://user-images.githubusercontent.com/58044383/174409181-ebfa4035-a01f-46b3-988b-a83324e9d624.png">
 
Раздаем интернет на сеть `77.77.77.0` с маской `/24` и с помощью маски разбиваем сеть на подсети. 
 + Общий диапазон `77.77.77.1 - 77.77.77.254`
 + Для компьютеров `ion` и `meson` с маской `255.255.255.128` (она же `/25`) устанавливаем диапазон `77.77.77.1 - 77.77.77.126` и из него выбираем любые три номера.
 + Оставшийся доступный диапазон `77.77.77.129 - 77.77.77.254`
 + Для роутеров `proton` и `boson` с маской `255.255.255.252` (она же `/30`) остается два IP-адреса `255.255.255.253` и `255.255.255.254`
 + Оставшийся доступный диапазон `77.77.77.129 - 77.77.77.250`
 + Для компьютера `cation` выбираем маску `255.255.255.192` (она же `/26`) и выбираем из диапазона `77.77.77.129 - 77.77.77.191` любые два номера.
 
 или
 
 <img width="1161" alt="image" src="https://user-images.githubusercontent.com/58044383/174454990-d4f47af6-344e-4e9c-93e0-8d9be9afa920.png">
</details>
<details>
<summary>Level 10</summary>
<img width="982" alt="image" src="https://user-images.githubusercontent.com/58044383/174407805-e7680d91-57c6-45b1-8335-f10fd540801d.png">
 или
 <img width="1276" alt="image" src="https://user-images.githubusercontent.com/58044383/174455007-25f76134-d501-4331-8628-bb9da5078696.png">

</details>


Если я вам помог, ставьте звездочку)
