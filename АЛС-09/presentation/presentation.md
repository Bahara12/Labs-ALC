---
lang: ru-RU
title: Администрирование локальных сетей
subtitle: Лабораторная работа №9
author:
  - Абдуллахи Бахара
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 6 апреля 2026

toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цели и задачи работы

## Цель лабораторной работы

Изучение протокола STP и его модификации Rapid PVST+, настройка резервирования и агрегирования каналов.

# Выполнение лабораторной работы

## Формирование резервного соединения

![Резервное соединение](01.png){ width=70% }

## Проверка прохождения ICMP

![ICMP трафик](02.png){ width=70% }

## Анализ STP

![STP состояние](04.png){ width=70% }

## Назначение root-коммутатора

![Root bridge](05.png){ width=70% }

## Изменение маршрутов трафика

![Маршрутизация пакетов](06.png){ width=70% }

## Настройка PortFast

![PortFast](08.png){ width=70% }

## Проверка отказоустойчивости STP

![STP отказ](09.png){ width=70% }

## Переключение на Rapid PVST+

![Rapid PVST+](10.png){ width=70% }

## Проверка Rapid PVST+

![Rapid PVST test](11.png){ width=70% }

## Настройка EtherChannel

![EtherChannel настройка](12.png){ width=70% }

## Результат агрегирования

![EtherChannel результат](13.png){ width=70% }

## Проверка соединения

![Ping результат](14.png){ width=70% }

# Выводы

## Вывод

Настроена отказоустойчивая сеть с использованием STP и Rapid PVST+.  
Реализовано резервирование каналов и агрегирование EtherChannel.  
Проверена корректная работа сети при отказах и восстановлении соединений.