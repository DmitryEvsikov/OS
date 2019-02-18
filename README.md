# Лабораторные работы по дисциплине "Операционные системы"

## Задание 0

### Создать профиль на github

### Подготовить репозиторий для хранения лабораторных работ

#### Структура репозитория

Все лабораторные работы хранятся в одном репозитории. Для каждой лабораторной работы выделяется отдельная папка, внутри которой находятся папки проектов программ, написанных в ходе её выполнения.

В папках проектов должны находиться только текстовые файлы, необходимые для сборки и выполнения программы - входные данные, файлы проектов и модулей. Исполняемых и бинарных файлов, получаемых в ходе сборки программы (.exe, .obj, .o, .pyc и тому подобных) в репозитории быть не должно.

#### Пример репозитория
```
/
├── lab_0
│   ├── cpp
|   │   ├── data.txt
|   │   ├── project.sol
|   │   └── main.cpp
│   └── python
|       ├── data.txt
|       └── program.py
├── lab_1
│   ├── project_1
|   │   ├── filename.ext
|   │   └── filename.ext
|   :
│   └── project_N
|       ├── filename.ext
|       └── filename.ext
├── lab_2
├── lab_3
:
├── lab_N
└── README.md
```

### Выполнить задание на C++ и Python 3

Программа пытается восстановить сообщение, передаваемое в виде последовательности пакетов.
Каждый пакет имеет свой порядковый номер, но программе заранее не известен размер сообщения и номер первого и последнего пакета.
Пакеты могут идти в произвольном порядке и дублироваться.

После получения каждого следующего пакета программа пытается определить, возможно ли из всех полученных пакетов сформировать законченное сообщение, то есть, составляют ли все полученные пакеты единую последовательность в которой нет пропусков.

После получения очередного пакета программа должна вывести предположение о сообщении (номер его начального и конечного пакетов) и информацию в двух вариантах: либо сообщение получено полностью, либо сообщение не получено и не хватает пакетов с такими-то номерами.

Последовательность пакетов берётся из текстового файла следующего формата: в каждой строке файла содержится одно целое положительное число из диапазона от 0 до 32767, то есть короткое знаковое целое (signed short) .
Количество чисел не ограничено и может превышать 100.

#### Пример работы программы

Входной файл:
```
10
11
1
7
13
9
7
```

Результат работы программы:
```
Сообщение 10-10 получено полностью.
Сообщение 10-11 получено полностью.
Сообщение 1-11 не хватает пакетов 2, 3, 4, 5, 6, 7, 8, 9.
Сообщение 1-11 не хватает пакетов 2, 3, 4, 5, 6, 8, 9.
Сообщение 1-13 не хватает пакетов 2, 3, 4, 5, 6, 8, 9, 12.
Сообщение 1-13 не хватает пакетов 2, 3, 4, 5, 6, 8, 12.
Сообщение 1-13 не хватает пакетов 2, 3, 4, 5, 6, 8, 12.
```

Программа должна быть написана в виде консольного приложения на языках C++ и Python 3.

### Загрузить решение в репозиторий
