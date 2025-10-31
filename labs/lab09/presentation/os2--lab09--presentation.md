---
## Front matter
lang: ru-RU
title: Лабораторная работа №9 
subtitle: Управление SELinux
author:
  - Перфилов Александр Константинович | Группа НПИбд-03-24
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 31 октября 2025

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

## Цель работы:
Целью данной работы является получение навыков работы с контекстом безопасности и политиками SELinux.

## Задание

1. Продемонстрируйте навыки по управлению режимами SELinux.
2. Продемонстрируйте навыки по восстановлению контекста безопасности SELinux.
3. Настройте контекст безопасности для нестандартного расположения файлов вебслужбы.
4. Продемонстрируйте навыки работы с переключателями SELinux.

# Результаты и анализ лабораторной работы

## Управление режимами SELinux 

1. Для просмотра текущей информации о состоянии SELinux используем `sestatus -v`
   
![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/1.jpg)

## Управление режимами SELinux 

2. Изменение режима работы SELinux на разрешающий (Permissive)

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/2.jpg)

## Управление режимами SELinux 

3. Попробовали переключить режим работы SELinux: `setenforce 1`. Не могла переключаться между отключённым и принудительным режимом без перезагрузки системы.

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/5.jpg)

## Использование restorecon для восстановления контекста безопасности 

1. Просмотр контекста безопасности файла /etc/hosts: `ls -Z /etc/hosts`. 

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/10.jpg)

## Использование restorecon для восстановления контекста безопасности 

2. Исправление контекста безопасности `restorecon -v /etc/hosts`. Опция -v показала процесс изменения. Убедилась, что тип контекста изменился. Для массового исправления контекста безопасности на файловой системе используем `touch /.autorelabel`.

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/10.jpg)

## Настройка контекста безопасности для нестандартного расположения файлов веб-сервера 

1. Запуск веб-сервера и службы httpd.

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/16.jpg)

## Настройка контекста безопасности для нестандартного расположения файлов веб-сервера 

2. В терминале под учётной записью своего пользователя обращаемся к веб-серверу в текстовом браузере lynx: `lynx http://localhost`.

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/18.jpg)

## Настройка контекста безопасности для нестандартного расположения файлов веб-сервера 

3. В терминале с полномочиями администратора применяем новую метку контекста к /web: `semanage fcontext -a -t httpd_sys_content_t "/web(/.*)?"`. Восстановливаем контекст безопасности.

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/19.jpg)

## Работа с переключателями SELinux 

1. Вывод списка переключателей SELinux для службы ftp: `getsebool -a | grep ftp`. 

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/22.jpg)

## Работа с переключателями SELinux 

2. Изменение текущего значения переключателя для службы ftpd_anon_write с off на on.

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/22.jpg)

## Работа с переключателями SELinux 

3. Изменение постоянного значение переключателя для службы ftpd_anon_write с off на on: `setsebool -P ftpd_anon_write on`.

![](/home/akpperfilov/work/study/2025-2026/Основы администрирования операционных систем/os2/study_2025-2026_os2/labs/lab09/presentation/image/22.jpg)

# Выводы
В ходе выполнения лабораторной работы были получены навыки работы с контекстом безопасности и политиками 
