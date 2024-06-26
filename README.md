# CourseWork Compilier - Компилятор подмножества процедурного языка

Данный проект представляет собой разработку компилятора для подмножества процедурного языка. Компилятор преобразует исходный код, написанный на этом языке, в промежуточное представление LLVM IR.

## Основные возможности

- Лексический и синтаксический анализ исходного кода
- Построение абстрактного синтаксического дерева (AST)
- Семантический анализ, включая проверку типов, областей видимости и корректности использования переменных и функций
- Генерация LLVM IR-кода
- Оптимизация сгенерированного кода (свертка констант, удаление лишних присваиваний, устранение заведомо ложных/истинных условий)

## Входной язык

Входной язык компилятора имеет следующие особенности:

- Поддерживаемые типы данных: `int` и `float`
- Операторы: арифметические, логические, условные, циклы, ввод-вывод
- Поддержка функций с возможностью возврата значений
- Блочная структура с использованием ключевых слов `Begin` и `End`

Более подробное описание входного языка можно найти в [отчете о разработке](Описание%20программы.docx).

## Использование

1. Разместите исходный код программы на входном языке в файле `input.toy` в папке проекта.
2. Запустите файл `main.py` для компиляции исходного кода.
3. Если компиляция прошла успешно, сгенерированный LLVM IR-код будет сохранен в файле `my_output.ll` в папке `llc`.

## Требования

Для функционирования компилятора необходимо наличие следующего программного обеспечения:

- Python 3.8
- Библиотеки PLY, llvmlite, NLTK

## Структура проекта

Проект состоит из следующих основных файлов:

- `lexer_parser.py`: Реализация лексического и синтаксического анализа.
- `ast.py`: Определение классов для представления абстрактного синтаксического дерева.
- `symbol_table.py`: Реализация таблицы символов.
- `codegen.py`: Генерация LLVM IR-кода.
- `main.py`: Точка входа, вызывающая последовательные этапы компиляции.
