---
## Front matter
title: "Лабораторная работа №4"
subtitle: "Подготовка экспериментального стенда GNS3"
author: "Спелов Андрей Николаевич"

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
papersize: a4
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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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

Целью данной работы является установка и настройка GNS3 и сопутствующего программного обеспечения.

# Выполнение лабораторной работы

Выполним установку GNS3 через менеджер пакетов Chocolatey для ОС Windows. Для этого запустим PowerShell с полномочиями администратора. В командной строке введём: choco install gns3 -y. После запуска графического окна по установке проследуем указаниям, нажимая Next, принимая соглашение по лицензии, выбирая отображение названия каталога в стартовом меню (оставляем выдаваемое по умолчанию)(рис. [-@fig:001]).

![Запуск PowerShell с полномочиями администратора. Ввод команды. Запуска графического окна по установке.](image/1.png){#fig:001 width=70%}

В процессе установки при выборе комплектации отметим MSVC Runtime (отмечено по умолчанию), GNS3-Desktop, GNS3-VM, Tools (рис. [-@fig:002]).

![Выбор комплектации MSVC Runtime, GNS3-Desktop, GNS3-VM, Tools.](image/2.png){#fig:002 width=70%}

Затем укажем расположение устанавливаемого пакета (оставим выдаваемое по умолчанию). В следующем окне требуется отметить тип виртуальной машины. Укажем VirtualBox, затем нажмём Inslall. Начнётся процесс установки GNS3 и дополнительных пакетов. При необходимости нажимаем Next, принимаем соглашение по лицензии для устанавливаемого программного обеспечения. В конце процесса установки появится окно с предложением запуска GNS3 после установки, мы снимаем галочку, нажимаем Finish.(рис. [-@fig:003]).

![Выбор типа виртуальной машины.](image/3.png){#fig:003 width=70%}

Версия виртуальной машины GNS3 VM для VirtualBox должна соответствовать версии клиентской и серверной частей GNS3-all-in-one. Загрузим соответствующую версию с сайта GNS3 https://gns3. com/software/download-vm(рис. [-@fig:004]).

![Загрузка соответствующей версии GNS3 VM с сайта GNS3.](image/4.png){#fig:004 width=70%}

Перейдём в каталог, в который скачан архив с образом виртуальной машины GNS3.VM.VirtualBox.2.2.54.zip и распакуем архив с образом. Запустим VirtualBox. Выберем: Меню-Файл-Импорт конфигураций. Укажем месторасположение распакованного образа GNS3 VM.ova (рис. [-@fig:005]).

![Запуск VirtualBox. Указание месторасположения распакованного образа GNS3 VM.ova.](image/5.png){#fig:005 width=70%}

В следующем окне в параметрах импорта выберем в политике MAC-адреса «Сгенерировать новые MAC-адреса всех сетевых адаптеров». Нажмём Импорт (рис. [-@fig:006]).

![Выбор в параметрах импорта политики MAC-адреса «Сгенерировать новые MAC-адреса всех сетевых адаптеров».](image/6.png){#fig:006 width=70%}

Уточним параметры настройки виртуальной машины GNS3 VM в VirtualBox. Для этого в VirtualBox выберем импортированную виртуальную машину и перейдите в меню: Машина-Настроить. Перейдём к опции «Система». Следуя рекомендациям, внесём исправления. Увеличим видеопамять виртуальной машины и изменим тип графического контроллера на рекомендуемый VMSVGA. Минимальные ресурсы для виртуальной машины: основная память — не менее 2048 МБ, число процессоров — не менее 8 ЦП (рис. [-@fig:007]).

![Внесение исправлений в системе.](image/7.png){#fig:007 width=70%}

Убедимся, что в VirtualBox в графическом интерфейсе флажок «Включить Nested VT-x/AMD-V» отмечен включённым(рис. [-@fig:008]).

![Проверка отметки на флажке «Включить Nested VT-x/AMD-V».](image/8.png){#fig:008 width=70%}

Запустим GNS3 VM в VirtualBox  (рис. [-@fig:009]).

![Запуск GNS3 VM в VirtualBox.](image/9.png){#fig:009 width=70%}

Затем в нашей основной операционной системе запустим приложение gns3 и выполним настройку(рис. [-@fig:010]).

![Запуск приложения gns3 в основной ОС и выполнение настройки.](image/10.png){#fig:010 width=70%}

Выключим GNS3 через меню: File-Quit. При этом виртуальная машина GNS VM выключилась сама(рис. [-@fig:011]).

![Выключение GNS3 и виртуальной машины GNS VM.](image/11.png){#fig:011 width=70%}

Добавим образ маршрутизатора (FRRouting). В рабочем пространстве GNS3 на левой боковой панели выберем просмотр маршрутизаторов (Browse Routers), затем нажмём на + New template(рис. [-@fig:012]).

![Добавление образа маршрутизатора (FRRouting).](image/12.png){#fig:012 width=70%}

В открывшемся окне укажем рекомендуемое верхнее значение, а именно, установить образ с GNS3-сервера, нажмём Next. В следующем окне выберем Routers и образ FRR (FRRouting), нажмём Install.  (рис. [-@fig:013]).

![Выбор Routers и образа FRR (FRRouting).](image/13.png){#fig:013 width=70%}

В следующем окне укажем, что устанавливать образ следует на виртуальную машину GNS3 VM, нажмём Next. Далее предлагается выбор эмулятора, оставляем предложенное, нажмём Next. В следующем окне предлагается перечень файлов для скачивания и последующей установки. Выберем наиболее актуальную версию и нажмём Download(рис. [-@fig:014]).

![Выбор актуальной версии.](image/14.png){#fig:014 width=70%}

После окончания скачивания (процесс скачивания отобразился в браузере нашей основной ОС) можно импортировать образ, затем нажмём Next(рис. [-@fig:015]).

![Импортирование образа.](image/15.png){#fig:015 width=70%}

В рабочем пространстве на левой панели в списке маршрутизаторов появился образ устройства FRR. Далее необходимо настроить образ маршрутизатора. Правой кнопкой мыши щёлкнем на образ устройства, в меню выберем Configure template. В открывшемся окне необходимо во вкладке «General settings» в поле «On close» выбрать Send the shutdown signal (ACPI).(рис. [-@fig:016]).

![Изменение в поле «On close» на Send the shutdown signal (ACPI).](image/16.png){#fig:016 width=70%}

Во вкладке «HDD» необходимо поставить галочку «Automatically create a config disk on HDD»(рис. [-@fig:017]).

![Отметка на параметре «Automatically create a config disk on HDD».](image/17.png){#fig:017 width=70%}

Далее в GNS3 требуется добавить образ платформы маршрутизации VyOS Для учебных заведений и некоммерческих организаций возможен бесплатный доступ к релизам.Добавим образ маршрутизатора (VyOS). В рабочем пространстве GNS3 на левой боковой панели выберем просмотр маршрутизаторов (Browse Routers), затем нажмём на + New template. В открывшемся окне укажем рекомендуемое верхнее значение, а именно, установить образ с GNS3-сервера, нажмём Next. В следующем окне выберем Routers и образ VyOS, нажмём Install (рис. [-@fig:018]).

![Выбор Routers и образа VyOS.](image/18.png){#fig:018 width=70%}

В следующем окне укажем, что устанавливать образ следует на виртуальную машину GNS3 VM, нажмём Next. Далее в окне выбора эмулятора выскакивает ошибка KVM(ее невощможно обойти и приходится отменить установку)(рис. [-@fig:019]).

![Ошибка в процессе выбора эмулятора](image/19.png){#fig:019 width=70%}

# Выводы

В ходе выполнения лабораторной работы мы научились устанавливать и настраивать GNS3 и сопутствующее программной обеспечение.

# Список литературы{.unnumbered}

::: {#refs}
:::
