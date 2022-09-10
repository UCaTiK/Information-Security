---
# Front matter
title: "Лабораторная работа 1"
author: "Юдин Герман Станиславович, НФИбд-01-19"

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

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

##### РОССИЙСКИЙ УНИВЕРСИТЕТ ДРУЖБЫ НАРОДОВ
##### Факультет физико-математических и естественных наук  
##### Кафедра прикладной информатики и теории вероятностей 
##### ПРЕЗЕНТАЦИЯ ПО ЛАБОРАТОРНОЙ РАБОТЕ №1

дисциплина: Информационная безопасность

Преподователь: Кулябов Дмитрий Сергеевич

Cтудент: Юдин Герман Станиславович

Группа: НФИбд-01-19

МОСКВА

2022 г.

# **Прагматика выполнения лабораторной работы**

- установка Rocky
- анализ загрузки системы

# **Цель работы**

Проанализировать последовательность загрузки системы.

# **Выполнение лабораторной работы**

# 1. Версия ядра Linux (Linux version)

Версия оказалась Linux 5.14.0-70.22.1.el9_0.x86_64

![Linux Version](img/1.png "Linux Version")

# 2. Частота процессора (Detected Mhz processor)

Почти 2500 Мега герц.

![Detected Mhz processor](img/2.png "Detected Mhz processor")

# 3. Модель процессора (CPU0)

Процессор - Xeon CPU E5-2678 v3

![CPU0](img/3.png "CPU0")

# 4. Объем доступной оперативной памяти (Memory available)

Свободной памяти 3.5 Гб, а всего 8 Гб.

![Memory available](img/4.png "Memory available")

# 5. Тип обнаруженного гипервизора (Hypervisor detected)

Hypervisor detected: KVM

![Hypervisor detected](img/5.png "Hypervisor detected")

# 6. Тип файловой системы корневого раздела

Для нашего диска, а именно sda1, тип файловой системы XFS.

![XFS](img/6.png "XFS")

# 7. Последовательность монтирования файловых систем

Сначала монтируется Huge Pages FS, POSIX Message Queue FS, Kernel Debug FS, Kernel Trace FS и наконец Root and Kernel FS

![Mount FileSystem](img/7.png "Mount FileSystem")

# Выводы

Выполнив данную лабораторную работу, я установил Rocky на виртуальную машину, а также изучил последовательность загрузки операционной системы.
