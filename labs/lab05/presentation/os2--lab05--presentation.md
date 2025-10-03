---
## Front matter
lang: ru-RU
title: Лабораторная работа №5
subtitle: Управление системными службами
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

- Управление системными службами

## ## Цель работы

- Получить навыки управления системными службами операционной системы посред-
ством systemd.

## Ход лабораторной работы

## Управление сервисами

## Заходим в root

- Заходим под уч запись root

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/1.jpg){#fig:001 width=71%}

## Служба Very Secure FTP

 - Проверяем статус службы Very Secure FTP
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/2.jpg){#fig:001 width=71%}
 
## Установка службы Very Secure FTP

- Установливаем службу Very Secure FTP

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/3.jpg){#fig:001 width=71%}

## Запуск службы Very Secure FTP

- Запускаем службу Very Secure FTP

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/4.jpg){#fig:001 width=71%}

## Проверяем статус службы Very Secure FTP

- Проверяем статус с помощью systemctl status vsftpd

- Вывод команды должен показать, что служба в настоящее время работает, но не будет
активирована при перезапуске операционной системы

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/5.jpg){#fig:001 width=71%}


## Добавляем службу Very Secure FTP в автозапуск при загрузке операционной системы
 
- Используем команду systemcl enable vsftpd

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/6.jpg){#fig:001 width=71%}
 
## Выведем на экран символические ссылки, ответственные за запуск различных сервисов

- Выводим с помощью команды ls /etc/systemd/system/multi-user.target.wants
![](//home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/7.jpg){#fig:001 width=71%}

## Добавляем службу Very Secure FTP в автозапуск

- Вводим команду systemctl enable vsftpd

 ![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/8.jpg){#fig:001 width=71%}
 
## Проверяем статус службы Very Secure FTP

- Проверяем статус службы командой systemctl status vsftpd

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/9.jpg){#fig:001 width=71%}

- МЫ увидим что для файла юнита состояние изменено с disabled на enabled

## Выводим на экран список зависимостей юнита
 
 - Используем команду systemctl list-dependencies vsftpd
 
 ![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/10.jpg){#fig:001 width=71%}  

## Выводим на экран список юнитов, которые зависят от данного юнита

- Используем команду systemctl list-dependencies vsftpd --reverse
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/11.jpg){#fig:001 width=71%}


## Получаем полномочия администратора и устанавливаем iptables

- Для установки вводим dnf -y install iptables\*
 
![](//home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/12.jpg){#fig:001 width=71%}

## Проверяем статус firewalld :

- Проверяем статус с помощью команды systemctl status firewalld

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/13.jpg){#fig:001 width=71%}
 
## запускаем firewalld и iptables

- Запускаем firewald с помощью systemctl start firewalld
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/14.jpg){#fig:001 width=30%}

- Запускаем iptables с помощью systemctl start iptables

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/15.jpg){#fig:001 width=30%}

## Вводим команду cat /usr/lib/systemd/system/firewalld.service

- Ищем настройки конфликтов юнита firewalld
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/16.jpg){#fig:001 width=71%}
  
## Вводим команду cat /usr/lib/systemd/system/iptables.service

- Ищем настройки конфликтов юнита для iptables
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/17.jpg){#fig:001 width=71%}

## Выгружаем службу iptables

- Для выгрузки iptables используем systemctl stop iptables
 
![](//home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/18.jpg){#fig:001 width=71%}
  
## Загружаем службу firewalld

- Загружаем службу firewald
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/19.jpg){#fig:001 width=71%}
  
## Блокируем запуск iptables

- Блокируем запуск введя systemctl mask iptables
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/20.jpg){#fig:001 width=71%}

## Попробуем запустить iptables:

- Пробуем запустить iptables
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/21.jpg){#fig:001 width=71%}


## Добавляем iptables в автозапуск:

- Добавляем iptables в автозапуск

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/22.jpg){#fig:001 width=71%}


## Входим в уч запись root и преходим в каталог systemd

- Через учетную запись root переходи в каталог

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/23.jpg){#fig:001 width=71%}
 
## Вводим команду grep isolate *.target

- Находим список целей которые можно изолировать

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/24.jpg){#fig:001 width=71%}

## Переключите операционную систему в режим восстановления

- Включаем режим восстановления

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/25.jpg){#fig:001 width=71%}
 

## Входим в уч запись root и вводим команду systemctl get-default

- Входим в root и вводим systemctl get-default

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/26.jpg){#fig:001 width=71%}

## Для установки цели по умолчанию используем systemctl set-default

- Устанавливаем цель с помощью systemctl set-default
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/27.jpg){#fig:001 width=71%}

## Для запуска по умолчанию текстового режима вводим systemctl setdefaultmulti-user.target

- Для запуска используеми systemctl setdefaultmulti-user.target
 
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/28.jpg){#fig:001 width=71%}

## Перезапускаем систему командой reboot

- Перезапускаем систему в графическом режиме

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab05/presentation/image/29.jpg){#fig:001 width=71%}


## Вывод:

В ходе работы приобретены умения по работе с управлением системными службами операционной системы посредством systemd
