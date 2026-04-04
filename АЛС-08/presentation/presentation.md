---
## Front matter
lang: ru-RU
title: Администрирование локальных сетей
subtitle: Лабораторная работа №8
author:
  - Абдуллахи Бахара
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 29 марта 2026

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
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

Приобретение навыков настройки сетевых сервисов DHCP и DNS в локальной сети.

# Выполнение лабораторной работы

## Схема сети

![Топология сети](01.png){ width=70% }

## Настройка DNS-сервера

![Настройка IP-адреса DNS-сервера](02.png){ width=70% }

## Настройка DNS-сервиса

![Настройка DNS](03.png){ width=70% }

## Настройка DHCP на маршрутизаторе

![Настройка DHCP](04.png){ width=70% }

## Получение IP по DHCP

![DHCP на ПК](05.png){ width=70% }

## Проверка соединения

![Ping](06.png){ width=70% }

## Проверка DHCP-пулов

![DHCP pools](07.png){ width=70% }

## Проверка DHCP binding

![DHCP binding](08.png){ width=70% }

## DHCP Discover

![DHCP Discover](09.png){ width=70% }

## DHCP Offer

![DHCP Offer](10.png){ width=70% }

## DHCP Request

![DHCP Request](11.png){ width=70% }

## DHCP ACK

![DHCP ACK](12.png){ width=70% }

## Процесс DHCP в симуляции

![Simulation](13.png){ width=70% }

# Выводы по проделанной работе

## Вывод

В ходе лабораторной работы была выполнена настройка DNS- и DHCP-сервисов. Настроен DNS-сервер с доменными записями, а также DHCP-сервер на маршрутизаторе с несколькими пулами адресов. Оконечные устройства успешно получают IP-адреса автоматически. Проверка связности и анализ DHCP-пакетов в режиме симуляции подтвердили корректную работу сети и настроенных сервисов.