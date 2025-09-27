---
## Front matter
lang: ru-RU
title: Лабораторная работа №4
subtitle: Работа с программными пакетами
author:
  - Перфилов Александр Константинович | Группа НПИбд-03-24
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 27 сентября 2025

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


# Вводная часть


## Объект и предмет исследования

- Работа с программными пакетами

## Цель работы

- Получить навыки работы с репозиториями и менеджерами пакетов.

# Ход лабораторной работы

## Заход в режим работы суперпользователя root

- Переходим в пользовательскую учетную запись root с помощью su -

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/1.jpg){#fig:001 width=71%}

## Переходим в каталог etc/yum.repos.d и изучаем

- Переходим в каталог /etc/yum.repos.d и изучаем информацию о них с помощью ls и cat название_репозитория.repo

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/2.jpg){#fig:001 width=20%}

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/3.jpg){#fig:001 width=20%}

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/4.jpg){#fig:001 width=20%}


## Выводим на экран список репозиториев

- Выводим списки репозиториев

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/5.jpg){#fig:001 width=71%}

## Ищем в каких пакетах есть слово user

- С помощью команды dnf search user ищем пакеты в которых присутствует слово user

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/6.jpg){#fig:001 width=71%}

## Устанавливаем nmap

- Проверяем информацию о nmap и устанавливаем nmap 

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/7.jpg){#fig:001 width=30%}

- Устанавливаем nmap\*

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/8.jpg){#fig:001 width=30%}


## Удаляем nmap 

- Удаляем nmap и nmap\*

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/9.jpg){#fig:001 width=30%}

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/10.jpg){#fig:001 width=30%}

## Устанавливаем группу пакетов RPM Development Tools

- Устанавливаем группу пакетов RPM Development Tools

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/11.jpg){#fig:001 width=20%}

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/12.jpg){#fig:001 width=20%}

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/13.jpg){#fig:001 width=20%}

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/14.jpg){#fig:001 width=20%}

## Удаляем RPM Development Tools
- Удаляем ранее установленные пакеты RPM Development Tools

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/15.jpg){#fig:001 width=71%}

## Посмотрим информацию о dnf
- Смотрим информацию где и сколько раз использовался dnf

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/16.jpg){#fig:001 width=71%}

## Отмени последнее действие с dnf
- Отменяем последнее действие с dnf с помощью dnf history undo

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/17.jpg){#fig:001 width=71%}

## Устанавливаем текстовый браузер lynx

- Качаем группу rpm lynx

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/18.jpg){#fig:001 width=71%}


## Ищем в какой каталог был перемещен lynx
- Находим наш пакет в каталогах

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/19.jpg){#fig:001 width=71%}

## Переходим в каталог

- Переходим в каталог в котом находится lynx

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/20.jpg){#fig:001 width=71%}

## Устанавливаем rpm пакет
- Устанавливаем rpm пакет в каталоге в ктором находится lynx

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/21.jpg){#fig:001 width=71%}

## Находим наш файл
- Определяем расположение файла с помощью команды which lynx

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/22.jpg){#fig:001 width=71%}

## Определяем к какому пакету принадлежит lynx
- С помощью rpm определяем к какому пакету принадлежит lynx

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/23.jpg){#fig:001 width=30%}

- Получаем дом информацию с помощью rpm -qi lynx

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/24.jpg){#fig:001 width=30%}

## Список всех файлов
- Получаем список всех файлов в пакете

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/25.jpg){#fig:001 width=20%}

- Получаем перечень файлов с документацией пакета

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/26.jpg){#fig:001 width=20%}

- С помощью команды man lynx смотрим файлы документации

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/27.jpg){#fig:001 width=20%}

## Конфигурации пакетов

- Выводи на экран перечень и местоположение  конфигурационных файлов пакета

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/28.jpg){#fig:001 width=71%}

## Расположение скриптов

- Находим расположение и содержание скриптов

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/29.jpg){#fig:001 width=71%}

## Переходим в отдельный терминал

- Переходим в отдельный терминал и под своей учетной записью запускаем lynx

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/30.jpg){#fig:001 width=71%}

## Возвращаемся в root

- Возвращаемся в терминал root и удаляем пакеты lynx

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/31.jpg){#fig:001 width=71%}

## Устанавливаем dnsmasq

- Устанавливаем пакеты dnsmasq
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/32.jpg){#fig:001 width=30%}


- Определяем расположение файла с помощью which dnsmasq

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/33.jpg){#fig:001 width=30%}

## Определяем пакет с dnsmasq

- Определяем к какому пакету принадлежит dnsmasq

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/34.jpg){#fig:001 width=30%}

- Получаем доп информацию о содержимом пакета

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/35.jpg){#fig:001 width=30%}

## Список всех файлов в пакете

- Получаем список всех файлов в пакете

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/36.jpg){#fig:001 width=71%}

## Выводим перечень и местоположение

- Выводи перечень файлов с документацией пакета

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/37.jpg){#fig:001 width=71%}

## Конфигурационные файлы пакета

- Выводи на экран перечень и месторасположение конфигурационных файлов пакета

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/38.jpg){#fig:001 width=71%}


## Ищем скрипты при установке

- Выводим на экран расположение и содержание скриптов

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/41.jpg){#fig:001 width=71%}

## Удаление пакета в  учетной записи root

- Возвращаемся в терминал root и удаляем пакет rpm -e dnsmasq

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab04/presentation/image/последний.jpg){#fig:001 width=71%}

## Вывод:

В ходе работы приобретены умения по работе с репозиториями и менеджарами пакетов а также поиску информации о них
