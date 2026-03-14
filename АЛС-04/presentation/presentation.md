---
## Front matter
lang: ru-RU
title: Администрирование локальных сетей
subtitle: Лабораторная работа №4 — Первоначальное конфигурирование сети
author:
  - Абдуллахи Бахара
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 03 марта 2026

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Цель лабораторной работы

Провести подготовительную работу по первоначальной настройке коммутаторов сети и подготовить устройства к удалённому администрированию по SSH.

# Выполнение лабораторной работы

## Топология сети L1

![Топология сети L1](01.png){ width=75% }

## Типовая конфигурация коммутатора

На каждом коммутаторе выполнены действия:
- настройка hostname;
- создание интерфейса VLAN 2 и включение порта;
- назначение IP-адреса управления;
- настройка ip default-gateway;
- пароли для console и vty;
- enable secret и service password-encryption;
- пользователь admin;
- доменное имя;
- генерация RSA-ключей;
- разрешение доступа по SSH (transport input ssh);
- сохранение конфигурации (write memory).

# Настройка коммутаторов

## msk-donskaya-babdullakhi-sw-1

![Настройка msk-donskaya-babdullakhi-sw-1](02.png){ width=75% }

## msk-donskaya-babdullakhi-sw-2

![Настройка msk-donskaya-babdullakhi-sw-2](03.png){ width=75% }

## msk-donskaya-babdullakhi-sw-3

![Настройка msk-donskaya-babdullakhi-sw-3](04.png){ width=75% }

## msk-donskaya-babdullakhi-sw-4

![Настройка msk-donskaya-babdullakhi-sw-4](05.png){ width=75% }

## msk-pavlovskaya-babdullakhi-sw-1

![Настройка msk-pavlovskaya-babdullakhi-sw-1](06.png){ width=75% }

# Результаты

## Итоги выполнения работы

В ходе лабораторной работы:
- построена топология сети уровня L1 в Cisco Packet Tracer;
- выполнена первоначальная настройка 5 коммутаторов по единому шаблону;
- назначены IP-адреса управления на интерфейсе VLAN 2;
- настроены пароли и включён защищённый доступ по SSH;
- конфигурации сохранены в память устройств.

Коммутаторы готовы к удалённому администрированию в сети управления 10.128.1.0/24.
