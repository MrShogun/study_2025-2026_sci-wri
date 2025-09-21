---
## Front matter
title: "Лабораторная работа №1: Установка и настройка окружения LaTeX"
subtitle: "Computer Skills for Scientific Writing"
author: "Николаев Дмитрий Иванович"

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

Целью данной лабораторной работы является освоение процесса проверки и базовой настройки дистрибутива TeX Live в операционной системе Windows. Необходимо убедиться в корректности установки и доступности основных компонентов системы из командной строки, что является фундаментальным шагом для дальнейшей работы по созданию научных и технических документов с помощью системы вёрстки LaTeX.

# Теоретическое введение

## Структура LaTeX-документа

LaTeX — это система подготовки документов, которая позволяет авторам сосредоточиться на содержании, а не на визуальном оформлении. Документ в LaTeX имеет чёткую структуру, состоящую из преамбулы и тела. В преамбуле объявляется класс документа (`\documentclass`), подключаются необходимые пакеты (`\usepackage`), определяются заголовки и другая метаинформация. Тело документа заключается между командами `\begin{document}` и `\end{document}` и содержит сам текст, формулы, таблицы и изображения.

## Дистрибутив TeX Live

Для работы с LaTeX необходим дистрибутив — набор программ, шрифтов и пакетов. TeX Live является одним из самых полных и популярных кроссплатформенных дистрибутивов. Он включает в себя компилятор `pdflatex`, который преобразует исходный `.tex` файл в готовый к печати документ формата PDF, а также тысячи пакетов расширений для решения практически любых задач вёрстки.

## Переменная окружения PATH

Для того чтобы операционная система могла находить и запускать исполняемые файлы (такие как `pdflatex.exe`) из любого каталога через командную строку, пути к этим файлам должны быть добавлены в системную переменную окружения `PATH`. Установщик TeX Live обычно выполняет эту процедуру автоматически. Проверка успешности этой настройки является ключевой частью верификации установки.

# Выполнение лабораторной работы

Следуем указаниям из [@lab]. Так как дистрибутив TeX Live уже установлен в операционной системе, то основной задачей стала проверка его работоспособности.

## Проверка установки TeX Live

Согласно заданию, после установки TeX Live необходимо убедиться, что система настроена корректно. Лучший способ сделать это — выполнить команду для проверки версии одного из ключевых компонентов, компилятора `pdflatex`.

Для взаимодействия с системой на низком уровне была запущена командная строка. В открывшемся окне терминала была введена следующая команда:

```bash
pdflatex --version
```

Эта команда обращается к исполняемому файлу `pdflatex.exe` и запрашивает у него информацию о версии. Если система находит файл и успешно выполняет команду, это означает, что:

1. TeX Live установлен.
2. Путь к исполняемым файлам TeX Live корректно прописан в системной переменной PATH.

После выполнения команды в консоль был выведен текстовый блок с подробной информацией о версии компилятора и дистрибутива в целом. Результат представлен на рисунке [@fig:001].

![Результат проверки версии TeX Live](image/1.png){#fig:001 width=80%}

Как видно из вывода, система успешно определила версию pdfTeX (3.141592653-2.6-1.40.24) и дистрибутив TeX Live 2022. Это подтверждает, что окружение LaTeX полностью готово к работе.

# Выводы

В ходе выполнения данной лабораторной работы была успешно проведена проверка корректности установки дистрибутива TeX Live в операционной системе Windows. Путём вызова команды `pdflatex --version` было подтверждено, что ключевые компоненты системы доступны из командной строки, а системные пути настроены правильно.

# Список литературы{.unnumbered}

::: {#refs}
:::
