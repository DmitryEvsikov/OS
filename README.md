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

Перед загрузкой программ в репозиторий, убедитесь, что они запускаются и выдают правильный результат для тестового файла. 

### Загрузить решение в репозиторий

#### Делаем локальную копию созданного вами репозитория.

На странице вашего репозитория нажимаем кнопку "Clone or download", на выпадающей панели нажимаем кнопку копирования адреса репозитория в буфер обмена.

![Рисунок 1](/img/rp_01.gif)

Выбираем папку на вашем компьютере, в которой будет размещена локальная копия репозитория (в моём случае это c:\study), правой кнопкой мыши вызываем контекстное меню и выбираем пункт "Git Bash Here".

![Рисунок 2](/img/rp_02.gif)

Появится окно консоли Bash, запущенной в этой папке (можно убедиться по записи /c/study в строке запроса), из которой мы будем выполнять комманды git.

![Рисунок 3](/img/rp_03.gif)

Набираем в консоли git clone и вставляем из буфера обмена скопированный адрес. Для выполнения команды клонирования нажимаем ввод.

![Рисунок 4](/img/rp_04.gif)

После клонирования репозитория появляется папка, с именем, совпадающим с именем репозитория и содержащая его локальную копию. В моём случае это папка c:/study/test_repo

![Рисунок 5](/img/rp_06.gif)

Переходим эту папку консольной командой

```bash
cd test_repo
```

или открываем новую консоль Bash через локальное меню этой папки.

![Рисунок 6](/img/rp_05.gif)

Обратите внимание, что в папке, содержащей репозиторий, в строке запроса теперь указывается не только путь к ней /c/study/test_repo, но и та ветвь репозитория, с которой мы будем работать (master).

#### Синхронизация локального репозитория с github

После того, как мы сделали локальную копию репозитория, мы можем вносить в неё любые изменения и помещать нужные нам файлы и папки. Каждый раз, чтобы синхронизировать изменения, внесённые в локальный репозиторий с репозиторием на github нужно выполнить следующие команды.

```bash
git add .
```

Сканирует локальный репозиторий, находит все новые и изменённые папки и файлы и добавляет их в список.

```bash
git commit -m "Описание изменений"
```

Добавляет все найденные на предыдущем шаге изменения и их краткое описание в локальный репозиторий.

```bash
git push
```

Загружает локальные изменения в репозиторий на github. Во время выполнения этой комманды вас спросят логин и пароль от вашего профиля на github.

### Сообщить мне адресс вашего репозитория

После того, как вы создали репозиторий, дальнейшее обсуждение ваших лабораторных работ мы будем вести уже на github, на странице вашего репозитория, во вкладке Issues.

## Лабораторная работа 1.

Получение информации о параметрах аппаратных средств в системе Windows с помощью низкоуровневого API.

### Пример

https://docs.microsoft.com/en-us/windows/desktop/api/sysinfoapi/

Функция GetSystemInfo, возвращает информацию о системе.
Функция находится в динамической библиотеке Kernel32.dll и может быть вызвана из С или С++ с помощью подключения заголовочного файла sysinfoapi.h или windows.h, который его включает в себя.

Формат вызова функции

```cpp
void GetSystemInfo(LPSYSTEM_INFO lpSystemInfo);
```

В качестве параметра функции передаётся ссылка на структуру SYSTEM_INFO, которая заполняется информацией осистеме.

Структура SYSTEM_INFO содержит информацию о используемом компьютере. Эта информация включает архитектуру и тип процессора, количество процессоров в системе, размер страницы памяти и прочую подобную информацию.

```cpp
typedef struct _SYSTEM_INFO {
  union {
    DWORD dwOemId; // Неиспользуемое поле, оставлено для совместимости
    struct {
      WORD wProcessorArchitecture; // Архитектура процессора
      WORD wReserved; // Зарезервировано для будущего использования
    } DUMMYSTRUCTNAME;
  } DUMMYUNIONNAME;
  DWORD     dwPageSize; // Размер страницы памяти в байтах
  LPVOID    lpMinimumApplicationAddress; // Указатель на минимальный адрес памяти, доступный приложениям
  LPVOID    lpMaximumApplicationAddress; // Указатель на максимальный адрес памяти, доступный приложениям
  DWORD_PTR dwActiveProcessorMask; // Указатель на битовую маску, состоящую из 32 бит, каждый из которых отображает доступность процессора системе
  DWORD     dwNumberOfProcessors;  // Количество логических процессоров (вычислительных ядер) в системе
  DWORD     dwProcessorType;  // Неиспользуемое поле, оставлено для совместимости
  DWORD     dwAllocationGranularity; // Минимальный шаг адреса, используемый для выделения виртуальной памяти
  WORD      wProcessorLevel; // Уровень процессора, значение которого зависит от архитектуры
  WORD      wProcessorRevision; // Ревизия процессора, значение которой зависит от архитектуры
} SYSTEM_INFO, *LPSYSTEM_INFO;
```

Обратите внимание, что в структурах данных, используемых низкоуровневыми API очень часто могут встречаться неиспользуемые поля, оставленные для совместимости с предыдущими версиями оперционной системы, а также неопределённые поля, зарезервированные для будущего использования.

Пример программы на С++, получающей мнформацию о системе с помощью функции GetSystemInfo

```cpp
#include <sysinfoapi.h>
#include <stdio.h>

int main(int argc, char** argv) {
    SYSTEM_INFO siSysInfo;
        
    GetSystemInfo(&siSysInfo); // Заполняем структуру SYSTEM_INFO информацией о системе. 
    
    // Выводим содержимое структуры SYSTEM_INFO 
    
    printf("Hardware information: \n");  
    printf("  Processor Architecture: %u\n", siSysInfo.wProcessorArchitecture);
    printf("  Number of processors: %u\n", siSysInfo.dwNumberOfProcessors); 
    printf("  Page size: %u\n", siSysInfo.dwPageSize); 
    printf("  Processor Level: %u\n", siSysInfo.wProcessorLevel); 
    printf("  Processor Revision: %u\n", siSysInfo.wProcessorRevision); 
    printf("  Minimum application address: %lx\n", siSysInfo.lpMinimumApplicationAddress); 
    printf("  Maximum application address: %lx\n", siSysInfo.lpMaximumApplicationAddress); 
    printf("  Active processor mask: %u\n", siSysInfo.dwActiveProcessorMask); 
    
    return 0;
}
```

Результат работы программы:

```
Hardware information:
  Processor Architecture: 9
  Number of processors: 4
  Page size: 4096
  Processor Level: 6
  Processor Revision: 14857
  Minimum application address: 10000
  Maximum application address: fffeffff
  Active processor mask: 15

```
Мы видим, что в данном случае архитектура процессора 9 (то есть, x64), количество логических процессоров - 4 (на самом деле это один процессор с двумя ядрами и поддержкой Hyper-threading).
Битовая маска активных процессоров содержит 15, то есть 00000000000000000000000000001111 в двоичной системе, что говорит нам о том что все четыре логических процессора (биты 0, 1, 2, 3) выставлены в 1 и значит доступны системе.

Теперь обратимся к той же функции GetSystemInfo из динамической библиотеке Kernel32.dll с помощью программы на Python.
Для этого воспользуемся стандартной библиотекой ctypes (https://docs.python.org/3/library/ctypes.html).

```python
from ctypes import windll, byref, Structure, Array, wintypes

# Опишем структуру SYSTEM_INFO в виде класса, с помощью типов данных Windows, описанных в ctypes.wintypes 

class SYSTEM_INFO(Structure):
    _fields_ = [("wProcessorArchitecture", wintypes.WORD),
                ("wReserved", wintypes.WORD),
                ("dwPageSize", wintypes.DWORD),
                ("lpMinimumApplicationAddress", wintypes.LPVOID),
                ("lpMaximumApplicationAddress", wintypes.LPVOID),
                ("dwActiveProcessorMask", wintypes.LPVOID),
                ("dwNumberOfProcessors", wintypes.DWORD),
                ("dwProcessorType", wintypes.DWORD),
                ("dwAllocationGranularity", wintypes.DWORD),
                ("wProcessorLevel", wintypes.WORD),
                ("wProcessorRevision", wintypes.WORD)]


# создаём переменную, являющуюся экзкмпляром класса SYSTEM_INFO
si = SYSTEM_INFO()

# загружаем динамическую библиотеку kernel32.dll
kernel32 = windll.kernel32

# вызываем функцию GetSystemInfo, передавая ей переменную si по ссылке 
kernel32.GetSystemInfo(byref(si))

# после вызова функции выводим содержимое полей структуры SYSTEM_INFO
print("%s: %s (0x%x)" % ("Processor Architecture", si.wProcessorArchitecture, si.wProcessorArchitecture))
print("%s: %s (0x%x)" % ("Number of Processors", si.dwNumberOfProcessors, si.dwNumberOfProcessors))
print("%s: %s (0x%x)" % ("Page Size", si.dwPageSize, si.dwPageSize))
print("%s: %s (0x%x)" % ("Processor Level", si.wProcessorLevel, si.wProcessorLevel))
print("%s: %s (0x%x)" % ("Processor Revision", si.wProcessorRevision, si.wProcessorRevision))
print("%s: %s (0x%x)" % ("Minimum Application Address", si.lpMinimumApplicationAddress, si.lpMinimumApplicationAddress))
print("%s: %s (0x%x)" % ("Maximum Application Address", si.lpMaximumApplicationAddress, si.lpMaximumApplicationAddress))
print("%s: %s (0x%x)" % ("Active Processor Mask", si.dwActiveProcessorMask, si.dwActiveProcessorMask))
```

Результат работы программы совпадает с результатом работы программы на c++ 

```
Processor Architecture: 9 (0x9)
Number of Processors: 4 (0x4)
Page Size: 4096 (0x1000)
Processor Level: 6 (0x6)
Processor Revision: 14857 (0x3a09)
Minimum Application Address: 65536 (0x10000)
Maximum Application Address: 2147418111 (0x7ffeffff)
Active Processor Mask: 15 (0xf)
```
### Задание
1. Проверить работоспособность программ из примера, разобраться с принципами их работы.

2. По аналогии с программами из примеров самостоятельно написать программу на языках C++ и Python, получающую доступный объём оперативной памяти с помощью функции GetPhysicallyInstalledSystemMemory.
Описание функции, способ её вызова и возвращаемые значения - https://docs.microsoft.com/en-us/windows/desktop/api/sysinfoapi/nf-sysinfoapi-getphysicallyinstalledsystemmemory
