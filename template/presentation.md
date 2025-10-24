---
## Front matter
lang: ru-RU
title: Лабораторная работа №8
subtitle: Настройка SMTP-сервера
author:
  - Спелов А. Н.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 24 октября 2025

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
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'

## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Спелов Андрей Николаевич
  * НПИбд-02-23 Студ. билет: 1132231839
  * Российский университет дружбы народов
  * [1132231839@pfur.ru](mailto:1132231839@pfur.ru)

:::
::: {.column width="30%"}
:::
::::::::::::::

# Вводная часть

## Цель работы

- Целью данной работы является установка и настройка GNS3 и сопутствующего программного обеспечения.

# Основная часть

## Установка GNS3

- Выполним установку GNS3 через менеджер пакетов Chocolatey для ОС Windows.

![](./image/1.png)

## Установка GNS3

- В процессе установки при выборе комплектации отметим MSVC Runtime (отмечено по умолчанию), GNS3-Desktop, GNS3-VM, Tools

![](./image/2.png)

## Установка GNS3

- Выбор типа виртуальной машины.

![](./image/3.png)

## Установка GNS3

- Загрузка соответствующей версии GNS3 VM с сайта GNS3.

![](./image/4.png)

## Установка GNS3

- Запуск VirtualBox. Указание месторасположения распакованного образа GNS3 VM.ova.

![](./image/5.png)

## Установка GNS3

- Выбор в параметрах импорта политики MAC-адреса «Сгенерировать новые MAC-адреса всех сетевых адаптеров».

![](./image/6.png)

## Установка GNS3

- Внесение исправлений в системе.

![](./image/7.png)

## Установка GNS3

- Проверка отметки на флажке «Включить Nested VT-x/AMD-V».

![](./image/8.png)

## Установка GNS3

- Запуск GNS3 VM в VirtualBox.

![](./image/9.png)

## Установка GNS3

- Запуск приложения gns3 в основной ОС и выполнение настройки.

![](./image/10.png)

## Установка GNS3

- Выключение GNS3 и виртуальной машины GNS VM.

![](./image/11.png)

## Добавление образа маршрутизатора FRR

- Добавление образа маршрутизатора (FRRouting).

![](./image/12.png)

## Добавление образа маршрутизатора FRR

- Выбор Routers и образа FRR (FRRouting).

![](./image/13.png)

## Добавление образа маршрутизатора FRR

- Выбор актуальной версии.

![](./image/14.png)

## Добавление образа маршрутизатора FRR

- Импортирование образа.

![](./image/15.png)

## Добавление образа маршрутизатора FRR

- Изменение в поле «On close» на Send the shutdown signal (ACPI).

![](./image/16.png)

## Добавление образа маршрутизатора FRR

- Отметка на параметре «Automatically create a config disk on HDD».

![](./image/17.png)

## Добавление образа маршрутизатора VyOS

- Выбор Routers и образа VyOS.

![](./image/18.png)

## Добавление образа маршрутизатора VyOS

- Далее в окне выбора эмулятора выскакивает ошибка KVM(ее невощможно обойти и приходится отменить установку)

![](./image/19.png)

# Вывод

## Вывод

- В ходе выполнения лабораторной работы мы научились устанавливать и настраивать GNS3 и сопутствующее программной обеспечение.