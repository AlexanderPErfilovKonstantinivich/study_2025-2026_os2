---
## Front matter
lang: ru-RU
title: Лабораторная работа №11 
subtitle: Управление загрузкой системы
author:
  - Перфилов Александр Константинович | Группа НПИбд-03-24
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 14 ноября 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: JuanLesPins
colortheme: beaver
fonttheme: professionalfonts
innertheme: rounded
outertheme: infolines

## Fonts
mainfont: Liberation Serif
romanfont: Liberation Serif
sansfont: Liberation Sans
monofont: Liberation Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Перфилов Александр Константинович
  * Группа НПИбд-03-24
  * Российский университет дружбы народов
  * <https://github.com/AlexanderPErfilovKonstantinivich?tab=repositories>

:::
::: {.column width="30%"}


:::
::::::::::::::

# Цель работы
 Получение навыков работы с загрузчиком системы GRUB2.
# Выполнение работы

## Модификация параметров GRUB2

![Запись в GRUB2 изменений](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/1.jpg){width=35%}

![Редактирование файла](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/2.jpg){width=35%}



##  Устранения неполадок

Перезапускаем систему, как только появится меню GRUB, выбираем строку с текущей версией ядра в меню и нажимаем e для редактирования. В конце строки ($root)/vmlinuz-  введем systemd.unit=rescue.target
и удалим опции rhgb

![Добавление systemd.unit=rescue.target](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/3.jpg){width=70%}



## Работа и изменения в Grub
![Продолжение загрузки. Файлы модулей](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/4.jpg){width=35%}


![Просмотр переменных сред и перезагрузка](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/5.jpg){width=35%}


##  Просмотр и редактирование строк

![Редактирование строки](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/6.jpg){width=35%}

![Просмотр загруженных модулей](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/7.jpg){width=35%}

## Изменения в Grud

![Добавление rd.break](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/8.jpg){width=70%}



## Сброс пароля ROOT

Чтобы получить доступ к системному образу для чтения и записи, наберем mount -o remount,rw /sysroot
Сделаем содержимое каталога /sysimage новым корневым каталогом, введем команду задания пароляи установим новый пароль для пользователя root. Загрузим также политику SELinux с помощью команды
load_policy -i и  вручную установим правильный тип контекста для /etc/shadow.

![Пароль для root](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/9.jpg){width=70%}

## Входим в root

После изменения пароля root перезагрузили систему и пытаемся войти в root с новым паролем.Мы смогли войти а значит мы все сделали правильно

![Вход в root после сброса пароля](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab11/presentation/image/10.jpg){width=70%}

# Вывод

## Вывод

- В ходе работы были получены навыки работы с загрузчиком системы, проделаны различные действия в GRUB2.
