---
## Front matter
title: "Отчёт по лабораторной работе 4"
subtitle: "Первоначальное конфигурирование сети"
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

Провести подготовительную работу по первоначальной настройке коммутаторов сети.

# Выполнение лабораторной работы

## Построение топологии сети

В логической рабочей области Cisco Packet Tracer была собрана сеть согласно схеме L1 (раздел 3.3).

В состав сети вошли следующие коммутаторы:
- msk-pavlovskaya-babdullakhi-sw-1  
- msk-donskaya-babdullakhi-sw-1  
- msk-donskaya-babdullakhi-sw-2  
- msk-donskaya-babdullakhi-sw-3  
- msk-donskaya-babdullakhi-sw-4  

Также были размещены оконечные устройства:
- рабочие станции подразделений (dk, dep, adm, other);
- серверы web, file и mail.

Соединения выполнены через соответствующие интерфейсы FastEthernet. Межкоммутаторные соединения организованы магистральными линиями, конечные устройства подключены к портам доступа.

![Топология сети L1](01.png)

## Первоначальная настройка коммутаторов

Настройка всех коммутаторов выполнена по типовой последовательности (пример 4.1) с изменением имени устройства и IP-адреса согласно плану адресации.

Для сети управления использована подсеть 10.128.1.0/24.  
Шлюз по умолчанию: 10.128.1.1.

На каждом коммутаторе выполнены следующие действия:
- создан и активирован интерфейс VLAN 2;
- назначен IP-адрес;
- настроен шлюз по умолчанию;
- заданы пароли на линии console и vty;
- установлен enable secret;
- включено шифрование паролей;
- создан пользователь admin;
- задано доменное имя donskaya.rudn.edu;
- сгенерированы RSA-ключи;
- разрешён доступ по SSH;
- конфигурация сохранена в память устройства.

## Настройка msk-donskaya-babdullakhi-sw-1

Коммутатору назначен IP-адрес 10.128.1.2/24.

![Настройка msk-donskaya-babdullakhi-sw-1](02.png)

После генерации RSA-ключей на линиях VTY разрешён доступ только по SSH.

## Настройка msk-donskaya-babdullakhi-sw-2

Коммутатору назначен IP-адрес 10.128.1.3/24.

![Настройка msk-donskaya-babdullakhi-sw-2](03.png)

Параметры безопасности и удалённого доступа настроены аналогично предыдущему устройству.

## Настройка msk-donskaya-babdullakhi-sw-3

Коммутатору назначен IP-адрес 10.128.1.4/24.

![Настройка msk-donskaya-babdullakhi-sw-3](04.png)

Включён SSH-доступ, выполнена генерация RSA-ключей, конфигурация сохранена.

## Настройка msk-donskaya-babdullakhi-sw-4

Коммутатору назначен IP-адрес 10.128.1.5/24.

![Настройка msk-donskaya-babdullakhi-sw-4](05.png)

После завершения настройки конфигурация сохранена в энергонезависимую память.

## Настройка msk-pavlovskaya-babdullakhi-sw-1

Коммутатору назначен IP-адрес 10.128.1.6/24.

![Настройка msk-pavlovskaya-babdullakhi-sw-1](06.png)

Настройка выполнена по аналогичной схеме: активация VLAN 2, назначение IP-адреса, настройка шлюза, конфигурирование линий console и vty, создание пользователя admin и включение SSH-доступа.

# Вывод

В результате выполнения лабораторной работы:
- построена топология сети уровня L1 согласно заданной схеме;
- настроены пять коммутаторов;
- каждому устройству назначен уникальный IP-адрес управления;
- реализована защита доступа с использованием паролей и SSH;
- конфигурации сохранены в память устройств.

Все коммутаторы готовы к удалённому администрированию по протоколу SSH в пределах сети управления 10.128.1.0/24.

# Контрольные вопросы

**1. При помощи каких команд можно посмотреть конфигурацию сетевого оборудования?**
Текущую (рабочую) конфигурацию оборудования можно просмотреть следующими командами:
– `show running-config` — отображает активную конфигурацию, находящуюся в оперативной памяти (RAM);
– `show run` — сокращённый вариант предыдущей команды;
– `show startup-config` — позволяет сравнить текущую и сохранённую конфигурации;
– `show ip interface brief` — выводит краткую информацию о состоянии интерфейсов и назначенных IP-адресах;
– `show version` — отображает сведения о версии IOS и параметрах устройства.

**2. При помощи каких команд можно посмотреть стартовый конфигурационный файл оборудования?**
Стартовая конфигурация хранится в энергонезависимой памяти (NVRAM). Для её просмотра используются команды:
– `show startup-config` — выводит сохранённую конфигурацию;
– `show start` — сокращённый вариант команды.

Эта конфигурация загружается при перезагрузке устройства.

**3. При помощи каких команд можно экспортировать конфигурационный файл оборудования?**
Экспорт конфигурации выполняется путём копирования файла на внешний сервер (TFTP, FTP, SCP и др.):
– `copy running-config tftp` — экспорт текущей конфигурации на TFTP-сервер;
– `copy startup-config tftp` — экспорт стартовой конфигурации;
– `copy running-config ftp` — передача файла на FTP-сервер;
– `copy startup-config scp` — копирование по защищённому протоколу SCP.

В процессе выполнения команды указываются IP-адрес сервера и имя файла.

**4. При помощи каких команд можно импортировать конфигурационный файл оборудования?**
Импорт конфигурации осуществляется обратной операцией копирования с сервера на устройство:
– `copy tftp running-config` — загрузка конфигурации с TFTP-сервера в текущую конфигурацию;
– `copy tftp startup-config` — загрузка файла в NVRAM;
– `copy ftp running-config` — импорт с FTP-сервера;
– `copy scp startup-config` — загрузка конфигурации по SCP.

После импорта при необходимости выполняется сохранение конфигурации командой `write memory` или `copy running-config startup-config`.
