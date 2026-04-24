---
## Front matter
title: "Отчёт по лабораторной работе 11"
subtitle: "Настройка NAT. Планирование"
author: "Абдуллахи Бахара"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Провести подготовительные мероприятия по подключению локальной сети организации к Интернету.

# Выполнение лабораторной работы

1. В проект Cisco Packet Tracer были внесены изменения в схему L1. В состав сети дополнительно включены сеть провайдера и модельная сеть Интернета. На схеме были указаны названия оборудования и порты подключения между устройствами.

   В верхней части схемы размещена модельная сеть Интернета, подключённая к коммутатору internet-babdullakhi-sw-1, который соединён с маршрутизатором провайдера provider-babdullakhi-gw-1. Далее сеть провайдера через коммутатор provider-babdullakhi-sw-1 соединена с маршрутизатором сети «Донская» msk-donskaya-babdullakhi-babdullakhi-gw-1.

   Также на схеме сохранены подключения внутренней инфраструктуры:
   – коммутатор msk-donskaya-babdullakhi-babdullakhi-sw-1 соединён с msk-pavlovskaya-babdullakhi-babdullakhi-sw-1;
   – коммутатор msk-donskaya-babdullakhi-babdullakhi-sw-1 соединён с msk-donskaya-babdullakhi-babdullakhi-sw-2;
   – коммутатор msk-donskaya-babdullakhi-babdullakhi-sw-2 соединён с msk-donskaya-babdullakhi-babdullakhi-sw-3;
   – коммутатор msk-donskaya-babdullakhi-babdullakhi-sw-1 соединён с msk-donskaya-babdullakhi-babdullakhi-sw-4.

   На схеме L1 были подписаны используемые интерфейсы FastEthernet и GigabitEthernet.

   ![Скорректированная схема L1](01.png){ #fig:001 width=80% }

2. Выполнена корректировка схемы L2 с указанием VLAN для внутренней сети, сети провайдера и модельной сети Интернета.

   Распределение VLAN:
   – VLAN 4 — сеть провайдера и Интернета;
   – VLAN 2 — сеть управления;
   – VLAN 3 — серверная ферма;
   – VLAN 101 — дисплейные классы;
   – VLAN 102 — кафедры;
   – VLAN 103 — администрация;
   – VLAN 104 — другие пользователи.

   На магистральных соединениях указаны разрешённые VLAN, на пользовательских портах — соответствующие VLAN.

   ![Скорректированная схема L2](02.png){ #fig:002 width=80% }

3. Выполнена корректировка схемы L3 с указанием адресного пространства сети.

   Используемые подсети:
   – Интернет — 192.0.2.0/24;
   – Провайдер — 198.51.100.0/24;
   – Серверная ферма — 10.128.0.0/24;
   – Сеть управления — 10.128.1.0/24;
   – Дисплейные классы — 10.128.3.0/24;
   – Кафедры — 10.128.4.0/24;
   – Администрация — 10.128.5.0/24;
   – Другие пользователи — 10.128.6.0/24.

   ![Скорректированная схема L3](03.png){ #fig:003 width=80% }

4. В логической рабочей области размещено оборудование для сети провайдера и модельного Интернета:
   – 4 медиаконвертера Repeater-PT;
   – 2 коммутатора Cisco 2960-24TT;
   – маршрутизатор Cisco 2811;
   – 4 сервера.

   Выполнено переименование устройств:
   – internet-babdullakhi-mc-1;
   – internet-babdullakhi-sw-1;
   – provider-babdullakhi-mc-1;
   – provider-babdullakhi-gw-1;
   – provider-babdullakhi-sw-1;
   – provider-babdullakhi-mc-2.

   Добавлены серверы:
   – www.yandex.ru;
   – stud.rudn.university;
   – www.rudn.ru;
   – esystem.rudn.ru;
   – babdullakhi-li-web;
   – babdullakhi-li-file;
   – babdullakhi-li-mail;
   – babdullakhi-dns.

   ![Размещение оборудования](04.png){ #fig:004 width=80% }

5. В физической рабочей области добавлены здания:
   – Provider;
   – Internet.

   ![Физическая схема](05.png){ #fig:005 width=80% }

6. Оборудование провайдера перенесено в здание Provider и соединено согласно схеме L1.

   Используемые устройства:
   – provider-babdullakhi-mc-1;
   – provider-babdullakhi-gw-1;
   – provider-babdullakhi-sw-1;
   – provider-babdullakhi-mc-2.

   ![Сеть провайдера](06.png){ #fig:006 width=80% }

7. Оборудование модельного Интернета размещено в здании Internet.

   Подключены серверы:
   – www.yandex.ru;
   – stud.rudn.university;
   – www.rudn.ru;
   – esystem.rudn.ru.

   Выполнено соединение с сетью провайдера.

   ![Сеть Интернета](07.png){ #fig:007 width=80% }

8. Выполнено соединение всех устройств согласно схеме L1. Сформирована единая сеть, включающая локальную сеть, сеть провайдера и модельную сеть Интернета.

   ![Итоговая схема](04.png){ #fig:008 width=80% }

9. Серверам назначены IP-адреса:

   – babdullakhi-li-web — 10.128.0.2;
   – babdullakhi-li-file — 10.128.0.3;
   – babdullakhi-li-mail — 10.128.0.4;
   – babdullakhi-dns — 10.128.0.5;
   – www.yandex.ru — 192.0.2.11;
   – stud.rudn.university — 192.0.2.12;
   – esystem.rudn.ru — 192.0.2.13;
   – www.rudn.ru — 192.0.2.14.

10. На DNS-сервере babdullakhi-dns настроены записи A:

   – dns.donskaya.rudn → 10.128.0.5;
   – file.donskaya.rudn → 10.128.0.3;
   – mail.donskaya.rudn → 10.128.0.4;
   – www.donskaya.rudn → 10.128.0.2;
   – www.yandex.ru → 192.0.2.11;
   – stud.rudn.university → 192.0.2.12;
   – esystem.rudn.ru → 192.0.2.13;
   – www.rudn.ru → 192.0.2.14.

   ![Настройка DNS](08.png){ #fig:009 width=80% }

## Таблица VLAN

| № VLAN | Имя VLAN     | Примечание                  |
|--------|--------------|-----------------------------|
| 1      | default      | Не используется             |
| 2      | management   | Для управления устройствами |
| 3      | servers      | Для серверной фермы         |
| 4      | provider      | Для сети провайдера         |
| 5–100  | —            | Зарезервировано             |
| 101    | dk           | Дисплейные классы (ДК)      |
| 102    | departments  | Кафедры                     |
| 103    | adm          | Администрация               |
| 104    | other        | Другие пользователи         |

## Таблица портов подключения оборудования

| Устройство             | Порт      | Примечание                         | Access VLAN | Trunk VLAN                  |
|------------------------|-----------|------------------------------------|-------------|-----------------------------|
| msk-donskaya-babdullakhi-gw-1      | f0/0      | к msk-donskaya-babdullakhi-sw-1                | —           | 2,3,101,102,103,104         |
| msk-donskaya-babdullakhi-gw-1      | f0/1      | к provider-babdullakhi-sw-1        | 4           | —                           |
| msk-donskaya-babdullakhi-sw-1      | f0/1      | к msk-pavlovskaya-babdullakhi-babdullakhi-sw-1 | —           | 2,101,104                  |
| msk-donskaya-babdullakhi-sw-1      | f0/24     | к msk-donskaya-babdullakhi-gw-1                | —           | 2,3,101,102,103,104         |
| msk-donskaya-babdullakhi-sw-1      | g0/1      | к msk-donskaya-babdullakhi-sw-2                | —           | 2,3                         |
| msk-donskaya-babdullakhi-sw-1      | g0/2      | к msk-donskaya-babdullakhi-sw-4                | —           | 2,101,102,103,104           |
| msk-donskaya-babdullakhi-sw-2      | g0/1      | к msk-donskaya-babdullakhi-sw-1                | —           | 2,3                         |
| msk-donskaya-babdullakhi-sw-2      | g0/2      | к msk-donskaya-babdullakhi-sw-3                | —           | 2,3                         |
| msk-donskaya-babdullakhi-sw-2      | f0/1      | Web-server                         | 3           | —                           |
| msk-donskaya-babdullakhi-sw-2      | f0/2      | File-server                        | 3           | —                           |
| msk-donskaya-babdullakhi-sw-3      | g0/1      | к msk-donskaya-babdullakhi-sw-2                | —           | 2,3                         |
| msk-donskaya-babdullakhi-sw-3      | f0/1      | Mail-server                        | 3           | —                           |
| msk-donskaya-babdullakhi-sw-3      | f0/2      | DNS-server                         | 3           | —                           |
| msk-donskaya-babdullakhi-sw-4      | g0/1      | к msk-donskaya-babdullakhi-sw-1                | —           | 2,101,102,103,104           |
| msk-donskaya-babdullakhi-sw-4      | f0/1–5    | ДК                                 | 101         | —                           |
| msk-donskaya-babdullakhi-sw-4      | f0/6–10   | Кафедры                            | 102         | —                           |
| msk-donskaya-babdullakhi-sw-4      | f0/11–15  | Администрация                      | 103         | —                           |
| msk-donskaya-babdullakhi-sw-4      | f0/16–24  | Другие пользователи                | 104         | —                           |
| msk-pavlovskaya-babdullakhi-sw-1   | f0/24     | к msk-donskaya-babdullakhi-sw-1                | —           | 2,101,104                  |
| msk-pavlovskaya-babdullakhi-sw-1   | f0/1–15   | ДК                                 | 101         | —                           |
| msk-pavlovskaya-babdullakhi-sw-1   | f0/20     | Другие пользователи                | 104         | —                           |
| provider-babdullakhi-sw-1 | f0/24  | к provider-babdullakhi-gw-1        | 4           | —                           |
| provider-babdullakhi-sw-1 | f0/1   | к msk-donskaya-babdullakhi-gw-1                | 4           | —                           |
| provider-babdullakhi-gw-1 | f0/0   | в сеть провайдера                  | 4           | —                           |
| provider-babdullakhi-gw-1 | f0/1   | в модельный Интернет               | —           | —                           |
| internet-babdullakhi-sw-1 | f0/24  | к provider-babdullakhi-gw-1        | —           | —                           |
| internet-babdullakhi-sw-1 | f0/1–10| серверы Интернета                  | —           | —                           |


# Вывод

В ходе лабораторной работы была модернизирована существующая сеть в Cisco Packet Tracer путём добавления сети провайдера и модельной сети Интернета. Были скорректированы схемы L1, L2 и L3, отражающие физическую, канальную и сетевую структуру сети.

В логической и физической рабочих областях было размещено дополнительное оборудование, включая маршрутизатор, коммутаторы, медиаконвертеры и серверы. Выполнено переименование устройств в соответствии с принятой схемой именования, а также организовано их размещение по зданиям и соединение согласно топологии сети.

Были настроены IP-адреса серверов как во внутренней сети, так и в модельной сети Интернета. На DNS-сервере добавлены записи, обеспечивающие разрешение доменных имён внутренних и внешних ресурсов.

В результате выполненной работы сформирована и настроена многоуровневая сеть, включающая локальную инфраструктуру, сеть провайдера и модельную сеть Интернета, что подтверждает корректность выполненной конфигурации и целостность сетевого взаимодействия.

# Контрольные вопросы

**1. Что такое Network Address Translation (NAT)?**  
Network Address Translation (NAT) — это технология преобразования сетевых адресов, при которой один или несколько внутренних (частных) IP-адресов заменяются внешним (публичным) IP-адресом при выходе в другую сеть, обычно в Интернет. Это позволяет экономить публичные IP-адреса и повышает безопасность внутренней сети.

**2. Как определить, находится ли узел сети за NAT?**  
Определить это можно следующими способами:  
– сравнить внутренний IP-адрес устройства с его внешним IP (например, через онлайн-сервисы);  
– если IP-адрес относится к частному диапазону (10.x.x.x, 172.16–31.x.x, 192.168.x.x), то узел, скорее всего, находится за NAT;  
– при трассировке маршрута (tracert/traceroute) можно увидеть промежуточные узлы с частными адресами;  
– отсутствие прямого входящего подключения извне также может указывать на использование NAT.

**3. Какое оборудование отвечает за преобразование адреса методом NAT?**  
Преобразование адресов выполняет маршрутизатор или специализированное сетевое устройство (например, межсетевой экран), расположенное на границе сети между внутренней и внешней средой.

**4. В чём отличие статического, динамического и перегруженного NAT?**  
– Статический NAT — обеспечивает постоянное соответствие одного внутреннего IP-адреса одному внешнему IP-адресу;  
– Динамический NAT — использует пул внешних адресов, которые временно назначаются внутренним устройствам при обращении во внешнюю сеть;  
– Перегруженный NAT (PAT, NAT Overload) — позволяет множеству внутренних устройств использовать один внешний IP-адрес за счёт различия по номерам портов.

**5. Охарактеризуйте типы NAT.**  
Основные типы NAT:  
– Static NAT — фиксированное отображение адресов один к одному;  
– Dynamic NAT — отображение из пула адресов по мере необходимости;  
– PAT (Port Address Translation) — отображение многих внутренних адресов на один внешний с использованием портов;  
– Inside NAT — применяется для преобразования адресов внутри сети;  
– Outside NAT — используется для преобразования внешних адресов относительно внутренней сети.