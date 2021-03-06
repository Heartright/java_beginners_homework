# Основная идея
Проходим по массиву от самого первого элемента и до самого конца. На шаге с номером *i* гарантируем, что элементы с номерами *от 0 до i* отсортированы. 
Для этого на каждом шаге просматриваем все элементы справа от текущего, и если находим какой-то меньший, то меняем их местами. К концу шага элемент с номером *i* будет меньше, чем любой с номером больше *i*.

# Краткая иллюстрация
```
Исходный массив: [4, 2, 3, 19, 4, 10, 0, 13, 19, 2].

[4, 2, 3, 19, 4, 10, 0, 13, 19, 2]
Шаг 0
[2, 4, 3, 19, 4, 10, 0, 13, 19, 2]
[0, 4, 3, 19, 4, 10, 2, 13, 19, 2]
Шаг 1
[0, 3, 4, 19, 4, 10, 2, 13, 19, 2]
[0, 2, 4, 19, 4, 10, 3, 13, 19, 2]
Шаг 2
[0, 2, 3, 19, 4, 10, 4, 13, 19, 2]
[0, 2, 2, 19, 4, 10, 4, 13, 19, 3]
Шаг 3
[0, 2, 2, 4, 19, 10, 4, 13, 19, 3]
[0, 2, 2, 3, 19, 10, 4, 13, 19, 4]
Шаг 4
[0, 2, 2, 3, 10, 19, 4, 13, 19, 4]
[0, 2, 2, 3, 4, 19, 10, 13, 19, 4]
Шаг 5
[0, 2, 2, 3, 4, 10, 19, 13, 19, 4]
[0, 2, 2, 3, 4, 4, 19, 13, 19, 10]
Шаг 6
[0, 2, 2, 3, 4, 4, 13, 19, 19, 10]
[0, 2, 2, 3, 4, 4, 10, 19, 19, 13]
Шаг 7
[0, 2, 2, 3, 4, 4, 10, 13, 19, 19]
Шаг 8
Шаг 9
[0, 2, 2, 3, 4, 4, 10, 13, 19, 19]
```

# Полная иллюстрация
```
Исходный массив: [4, 2, 3, 19, 4, 10, 0, 13, 19, 2].


>>>>>>>>>>>>
Шаг 0: сравниваем все элементы с номерами из (0...9] + с элементом 0.
Меняем местами элементы 0(4) и 1(2).
Теперь массив такой: [2, 4, 3, 19, 4, 10, 0, 13, 19, 2]
Элементы 0(2) и 2(3) расположены правильно.
Элементы 0(2) и 3(19) расположены правильно.
Элементы 0(2) и 4(4) расположены правильно.
Элементы 0(2) и 5(10) расположены правильно.
Меняем местами элементы 0(2) и 6(0).
Теперь массив такой: [0, 4, 3, 19, 4, 10, 2, 13, 19, 2]
Элементы 0(0) и 7(13) расположены правильно.
Элементы 0(0) и 8(19) расположены правильно.
Элементы 0(0) и 9(2) расположены правильно.
Шаг 0 окончен! Элемент с номером 0(0) стоит на своем месте!


>>>>>>>>>>>>
Шаг 1: сравниваем все элементы с номерами из (1...9] + с элементом 1.
Меняем местами элементы 1(4) и 2(3).
Теперь массив такой: [0, 3, 4, 19, 4, 10, 2, 13, 19, 2]
Элементы 1(3) и 3(19) расположены правильно.
Элементы 1(3) и 4(4) расположены правильно.
Элементы 1(3) и 5(10) расположены правильно.
Меняем местами элементы 1(3) и 6(2).
Теперь массив такой: [0, 2, 4, 19, 4, 10, 3, 13, 19, 2]
Элементы 1(2) и 7(13) расположены правильно.
Элементы 1(2) и 8(19) расположены правильно.
Элементы 1(2) и 9(2) расположены правильно.
Шаг 1 окончен! Элемент с номером 1(2) стоит на своем месте!


>>>>>>>>>>>>
Шаг 2: сравниваем все элементы с номерами из (2...9] + с элементом 2.
Элементы 2(4) и 3(19) расположены правильно.
Элементы 2(4) и 4(4) расположены правильно.
Элементы 2(4) и 5(10) расположены правильно.
Меняем местами элементы 2(4) и 6(3).
Теперь массив такой: [0, 2, 3, 19, 4, 10, 4, 13, 19, 2]
Элементы 2(3) и 7(13) расположены правильно.
Элементы 2(3) и 8(19) расположены правильно.
Меняем местами элементы 2(3) и 9(2).
Теперь массив такой: [0, 2, 2, 19, 4, 10, 4, 13, 19, 3]
Шаг 2 окончен! Элемент с номером 2(2) стоит на своем месте!


>>>>>>>>>>>>
Шаг 3: сравниваем все элементы с номерами из (3...9] + с элементом 3.
Меняем местами элементы 3(19) и 4(4).
Теперь массив такой: [0, 2, 2, 4, 19, 10, 4, 13, 19, 3]
Элементы 3(4) и 5(10) расположены правильно.
Элементы 3(4) и 6(4) расположены правильно.
Элементы 3(4) и 7(13) расположены правильно.
Элементы 3(4) и 8(19) расположены правильно.
Меняем местами элементы 3(4) и 9(3).
Теперь массив такой: [0, 2, 2, 3, 19, 10, 4, 13, 19, 4]
Шаг 3 окончен! Элемент с номером 3(3) стоит на своем месте!


>>>>>>>>>>>>
Шаг 4: сравниваем все элементы с номерами из (4...9] + с элементом 4.
Меняем местами элементы 4(19) и 5(10).
Теперь массив такой: [0, 2, 2, 3, 10, 19, 4, 13, 19, 4]
Меняем местами элементы 4(10) и 6(4).
Теперь массив такой: [0, 2, 2, 3, 4, 19, 10, 13, 19, 4]
Элементы 4(4) и 7(13) расположены правильно.
Элементы 4(4) и 8(19) расположены правильно.
Элементы 4(4) и 9(4) расположены правильно.
Шаг 4 окончен! Элемент с номером 4(4) стоит на своем месте!


>>>>>>>>>>>>
Шаг 5: сравниваем все элементы с номерами из (5...9] + с элементом 5.
Меняем местами элементы 5(19) и 6(10).
Теперь массив такой: [0, 2, 2, 3, 4, 10, 19, 13, 19, 4]
Элементы 5(10) и 7(13) расположены правильно.
Элементы 5(10) и 8(19) расположены правильно.
Меняем местами элементы 5(10) и 9(4).
Теперь массив такой: [0, 2, 2, 3, 4, 4, 19, 13, 19, 10]
Шаг 5 окончен! Элемент с номером 5(4) стоит на своем месте!


>>>>>>>>>>>>
Шаг 6: сравниваем все элементы с номерами из (6...9] + с элементом 6.
Меняем местами элементы 6(19) и 7(13).
Теперь массив такой: [0, 2, 2, 3, 4, 4, 13, 19, 19, 10]
Элементы 6(13) и 8(19) расположены правильно.
Меняем местами элементы 6(13) и 9(10).
Теперь массив такой: [0, 2, 2, 3, 4, 4, 10, 19, 19, 13]
Шаг 6 окончен! Элемент с номером 6(10) стоит на своем месте!


>>>>>>>>>>>>
Шаг 7: сравниваем все элементы с номерами из (7...9] + с элементом 7.
Элементы 7(19) и 8(19) расположены правильно.
Меняем местами элементы 7(19) и 9(13).
Теперь массив такой: [0, 2, 2, 3, 4, 4, 10, 13, 19, 19]
Шаг 7 окончен! Элемент с номером 7(13) стоит на своем месте!


>>>>>>>>>>>>
Шаг 8: сравниваем все элементы с номерами из (8...9] + с элементом 8.
Элементы 8(19) и 9(19) расположены правильно.
Шаг 8 окончен! Элемент с номером 8(19) стоит на своем месте!


>>>>>>>>>>>>
Шаг 9: сравниваем все элементы с номерами из (9...9] + с элементом 9.
Шаг 9 окончен! Элемент с номером 9(19) стоит на своем месте!


Результат: [0, 2, 2, 3, 4, 4, 10, 13, 19, 19].

Process finished with exit code 0
```
