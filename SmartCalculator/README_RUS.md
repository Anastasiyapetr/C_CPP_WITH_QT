# SmartCalculator

## Contents

1. [Introduction](#introduction)
2. [Implementation](#implementation) \
    2.1. [Реализация SmartCalc v1.0](#Реализация-SmartCalc-v1.0)  
    2.2. [Реализация кредитного калькулятора](#Реализация-кредитного-калькулятора)  
 

## Introduction

![SmartCalc](images/smartcalc.jpg)

В данном проекте на языке Си с использованием структурного подхода реализована расширенную версия обычного калькулятора, который можно найти в стандартных приложениях каждой операционной системы. Помимо базовых арифметических операций, дополнительно реализована  возможность вычисления арифметических выражений с учетом приоритетов, а так же некоторыми математическими функциями (синус, косинус, логарифм и т.д.). Помимо вычисления выражений калькулятор поддерживает использование переменной _x_ и построение графика соответствующей функции. В качестве дополнительных улучшений добавлена реализация кредитного калькудятора, который позволяет рассчитывать график платежей по кредиту.

## Implementation

### Реализация SmartCalc v1.0

- В основе вычислительной составляющей программы заложен алгоритм Дейкстры и алгоритм обратной польской нотации. 
- Программа разработана на языке Си стандарта C11 с использованием компилятора gcc с использованием дополнительных библиотек и модулей QT
- Сборка программы настроена с помощью Makefile со стандартным набором целей для GNU-программ: all, install, uninstall, clean, dvi, dist, test, gcov_report.
- Обеспечено покрытие unit-тестами модулей, связанных с вычислением выражений, с помощью библиотеки Check
- Реализация с графическим пользовательским интерфейсом, на базе GUI-библиотеки с API - QT;
- На вход программы могут подаваться как целые числа, так и вещественные числа, записанные через точку.
- Вычисление произвольных скобочных арифметических выражений в инфиксной нотации
- Вычисление произвольных скобочных арифметических выражений в инфиксной нотации с подстановкой значения переменной _x_ в виде числа
- Построение графика функции, заданной с помощью выражения в инфиксной нотации с переменной _x_  (с координатными осями, отметкой используемого масштаба и сеткой с адаптивным шагом)
- Максимальная длина арифметического выражения до 255 символов.
- Скобочные арифметические выражения в инфиксной нотации должны поддерживают следующие функции:
    - **Арифметические операторы**:

        | Название оператора | Инфиксная нотация <br /> (Классическая) | Префиксная нотация <br /> (Польская нотация) |  Постфиксная нотация <br /> (Обратная польская нотация) |
        | ------ | ------ | ------ | ------ |
        | Скобки | (a + b) | (+ a b) | a b + |
        | Сложение | a + b | + a b | a b + |
        | Вычитание | a - b | - a b | a b - |
        | Умножение | a * b | * a b | a b * |
        | Деление | a / b | / a b | a b \ |
        | Возведение в степень | a ^ b | ^ a b | a b ^ |
        | Остаток от деления | a mod b | mod a b | a b mod |
        | Унарный плюс | +a | +a | a+ |
        | Унарный минус | -a | -a | a- |

    - **Функции**:
  
        | Описание функции | Функция |   
        | ---------------- | ------- |  
        | Вычисляет косинус | cos(x) |   
        | Вычисляет синус | sin(x) |  
        | Вычисляет тангенс | tan(x) |  
        | Вычисляет арккосинус | acos(x) | 
        | Вычисляет арксинус | asin(x) | 
        | Вычисляет арктангенс | atan(x) |
        | Вычисляет квадратный корень | sqrt(x) |
        | Вычисляет натуральный логарифм | ln(x) | 
        | Вычисляет десятичный логарифм | log(x) |

### Реализация кредитного калькулятора

Предусмотрен специальный режим "Кредитный калькулятор", который выбирается из выпадающего списка в главном окне программы.

 - Вход: общая сумма кредита, срок, процентная ставка, тип (аннуитетный, дифференцированный)
 - Выход: ежемесячный платеж, переплата по кредиту, общая выплата
