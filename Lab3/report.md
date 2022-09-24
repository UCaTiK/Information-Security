---
# Front matter
title: "Лабораторная работа 3"
author: "Юдин Герман Станиславович, НФИбд-01-19"

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
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
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

<h1 align="center">
<p>РОССИЙСКИЙ УНИВЕРСИТЕТ ДРУЖБЫ НАРОДОВ 
<p>Факультет физико-математических и естественных наук  
<p>Кафедра прикладной информатики и теории вероятностей
<p>ОТЧЕТ ПО ЛАБОРАТОРНОЙ РАБОТЕ №3
<br></br>
<h2 align="right">
<p>дисциплина: Информационная безопасность
<p>Преподователь: Кулябов Дмитрий Сергеевич
<p>Студент: Юдин Герман Станиславович
<p>Группа: НФИбд-01-19
<br></br>
<br></br>
<h1 align="center">
<p>МОСКВА
<p>2022 г.
</h1>

# **Цель работы**

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.

# **Теоретическое введение**

useradd - добавление пользователя

passwd - установка пароля

gpasswd - добавление в группу

pwd - местоположение по файловой системе

whoami - узнать логин

id - информация о пользователе

newgrp - регистрация в группе

chmod - изменение атрибутов файла

# **Выполнение лабораторной работы**

1. На виртуальной машине создал нового пользователя guest2 и задал для него пароль (Рис [@fig:1])

![create user guest2](img/1.png "create user guest2"){ #fig:1 width=90% }

2. Добавил пользователя guest2 в группу guest (Рис [@fig:2])

![gpasswd](img/2.png "gpasswd"){ #fig:2 width=90% }

3. В одной консоли зашёл в систему с двух разных пользователей guest (Рис [@fig:3]) и guest2 (Рис [@fig:4])

![guest console](img/3.png "guest console"){ #fig:3 width=90% }

![guest2 console](img/4.png "guest2 console"){ #fig:4 width=90% }

4. С помощью pwd определил каталог у каждого (Рис [@fig:5] и [@fig:6]). Это оказались домашние директории.

![guest home directory](img/5.png "guest home directory"){ #fig:5 width=90% }

![guest2 home directory](img/6.png "guest2 home directory"){ #fig:6 width=90% }

5. Уточнил информацию об обоих пользователях. Пользователь guest - uid 1001, gid 1001, groups 1001 (Рис [@fig:7]). Пользователь guest2 - uid 1002, gid 1002, groups 1002 1001 (Рис [@fig:8]).

![guest information](img/7.png "guest information"){ #fig:7 width=90% }

![guest2 information](img/8.png "guest2 information"){ #fig:8 width=90% }

6. Проверил содержимое файла /etc/groups (Рис [@fig:9]), вывод совпал с результатами команд.

![groups file](img/9.png "groups file"){ #fig:9 width=90% }

7. От имени guest2 выполнил регистрацию в группе guest (Рис [@fig:10])

![newgrp](img/10.png "newgrp"){ #fig:10 width=90% }

8. От пользователя guest изменил права на домашнюю директории, добавив все права для группы пользователей (Рис [@fig:11]).

![chmod g+rwx](img/11.png "chmod g+rwx"){ #fig:11 width=90% }

9. Изменил права на директорию dir1 (Рис [@fig:12]) и начал эксперимент и заполнение таблицы

![chmod 000 dir1](img/12.png "chmod 000 dir1"){ #fig:12 width=90% }

10. В результате получил следующую таблицу (Рис [@fig:13] и [@fig:14]). Результаты оказались одинаковыми со второй лабораторной работой, так как отличия в правах нет, то есть одинаковые права у пользователя и группы пользователей дают одинаковые возможности для обеих сторон. Если пользователь может создавать файл и просматривать его с какими-либо правами, то и пользователь из его группы тоже сможет делать то же самое с равными правами.

![excel1](img/13.png "excel1"){ #fig:13 width=90% }

![excel2](img/14.png "excel2"){ #fig:14 width=90% }

11. Минимальные права выглядят следующим образом (Рис [@fig:15]).

![min requirements](img/15.png "min requirements"){ #fig:15 width=90% }

# Вывод

Выполнив данную лабораторную работу, я создал ещё одного пользователя и добавил его в группу другого пользователя, определил права, необходимые для действий с файлами и каталогами от группы пользователей.

# Список литературы

1. Кулябов, Д.С. - Лабораторная работа № 2. Дискреционное разграничение прав в Linux. Основные атрибуты
https://esystem.rudn.ru/pluginfile.php/1651885/mod_resource/content/4/003-lab_discret_2users.pdf
