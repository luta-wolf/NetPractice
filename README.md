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


В нижней части страницы вы увидите журналы. Они могут быть полезны, чтобы понять, почемуваша конфигурация неверна.


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
Это электронная база данных в маршрутизаторе, которая представляет из себя некий набор правил. В ней содержится информация о сетевых маршрутах по которым определяется наилучший путь для передачи пакета данных. Она содержит в себе адрес и маску сети подключения, адрес шлюза (т. е. маршрутизатора сети, на который отправляются данные), метрику (расстояние) и интерфейс (имя и индентификатор устройства).
 
### Коммутатор (switch)
Это устройство для соединения нескольких устройств в одной сети. У всех устройств одинаковая маска.

### Роутер (маршрутизатор)
Это сетевой компьютер, который обрабатывает полученные данные по заданным правилам администратора и опираясь на таблицу маршрутизации определяет путь для пересылки данных.
 
### Перед выполнением заданий помним:
+ Первый IP-адрес подсети - _адрес сети_
+ Последний IP-адрес подсети - _широковещательный_
+ IP-адреса соседних сетей не должны перекрываться
+ IP-адреса `10.0.0.0-10.255.255.255`, 
`172.16.0.0-172.31.255.255` и от `192.168.0.0` до `192.168.255.255` 
зарезервированы для частных адресов, диапазон `127.0.0.1-127.255.255.254`
зарезервирован
для коммуникации с самим собой, остальные-для публичных IP-адресов
+ У роутера для каждой подсети своя маска

### Примеры
IP-адрес `200.200.200.200/24`
+  `200.200.200.`0 - адрес сети
+  200.200.200.`255` - широковещательный адрес
+  200.200.200.`200` - адрес компьютера
+  `/24` - маска подсети на 254 компьютера (256 - 2 = 254)
+ 200.200.200.1 - 200.200.200.254 - диапазон адресов
 
IP-адрес `196.32.12.254/30`
 + `196.32.12`.0   - адрес сети
 + 196.32.12.`255` - широковещательный адрес
 + 196.32.12.`254`  - адрес компьютера
 + `/30` - маска подсети на 2 компьютера (4 - 2 = 2)
 + 196.32.12.253 - 196.32.12.254 - диапазон адресов
 
 ### Таблица маршрутизации
 <img width="962" alt="image" src="https://user-images.githubusercontent.com/58044383/174404596-36f3809d-a2ba-4c00-95bc-296f8914fba0.png">
 
Синее окно - таблица маршрутизации - правила, по которым определяется лучший путь для передачи пакетов.
 + `Слева` адрес и маска сети назначения (куда хотим отправить пакет).
 + `Справа` адрес шлюза (адрес роутера, куда направится пакет сразу).
 + В таблице маршрутизации `default` или `0.0.0.0/0` соответствуют всему
</details>



<details>
<summary>Полезные материалы</summary>
 
+ Почитать подробнее можно [здесь](https://github.com/evgenkarlson/ALL_SCHOOL_42/blob/master/00_Projects__(%D0%9E%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D0%BE%D0%B5_%D0%9E%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5)/00_Global_(begin_cadet)/02____netwhat/answers_to_netwhat.md).
+ Таблица соответствия [масок подсетей](https://www.gotoadm.ru/table-subnet-masks/).
+ IP [калькулятор](https://ip-calculator.ru/#!ip=192.168.114.253/30).
+ Лекция по [маршрутизации](https://www.youtube.com/watch?v=kZqqk1tixfk&ab_channel=AndreySozykin).
+ Лекция по [TCP/IP](https://www.youtube.com/watch?v=rLUzYeLdM0k&ab_channel=HillelITSchool).
+ Подробный курс лекций по [компьютерным сетям](https://www.youtube.com/watch?v=OLFA0soYGhw&list=PLtPJ9lKvJ4oiNMvYbOzCmWy6cRzYAh9B1&ab_channel=AndreySozykin).
</details>

### Если я вам помог, ставьте звездочку)
