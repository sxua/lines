# Lines

## Задача

Игра Lines: реализовать проверку наличия на поле линий.
Линией считается 5 или более шариков одного цвета, стоящих в ряд.

### Общее

- Данные подаются на стандартный вход программы (stdin), строки разделены символом новой строки \n
- Результат ожидается на стандартном выходе (stdout), в случае обнаружения линий нужно вывести их количество, если линии нет или данные указаны некорректно — вывести 0

### Ввод

Строка, начинающаяся с SIZE определяет размер поля.  
Строки, которые начинаются с BALL, определяют позицию и цвет шариков, которые уже есть на поле.  
За ними следуют строки, которые начинатся с MOVE, которые определяют передвижение шарика.  

Все координаты заданы числами, где первое число это ось x (сверху направо), второе — y (сверху вниз).  
В MOVE первая пара чисел это исходная ячейка, вторая пара — ячейка назначения.

```
+------ x
|
|
|
y
```

#### Пример

```
SIZE 5
BALL 0,0,red
BALL 0,1,green
BALL 0,2,blue
BALL 1,0,red
BALL 2,1,red
BALL 3,0,red
BALL 4,0,red
MOVE 0,1,1,1
MOVE 2,1,2,0
```

Изначальная расстановка шариков:

```
+---+---+---+---+---+
| r | r |   | r | r |
+---+---+---+---+---+
| g |   | r |   |   |
+---+---+---+---+---+
| b |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
```

После первого хода: линий нет

```
+---+---+---+---+---+
| r | r |   | r | r |
+---+---+---+---+---+
|   | g | r |   |   |
+---+---+---+---+---+
| b |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
```

После второго хода: есть одна линия

```
+---+---+---+---+---+
| r | r | r | r | r |
+---+---+---+---+---+
|   | g |   |   |   |
+---+---+---+---+---+
| b |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
```

Результат: 1

### Условия

- В каждой ячейке может быть только один шарик;
- Известно, что изначально на поле линий нет (можно не проверять), они могут появиться только после передвижения(ий);
- Известно, что на входе есть ровно одна строка SIZE, и как минимум по одной строке BALL и MOVE;
- Известно, что в качестве цветов используются слова red, green, blue и никакие другие;
- В случае дублирования шарика в ячейке нужно использовать последний;
- Остальные данные перед использованием нужно проверить. Могут быть указаны несуществующие позиции шариков, недействительные позиции передвижения, дублирование передвижения и т.д.;
- Победители определяются на основе правильного прохождения всех тестов. Главный победитель тот, чья программа работает быстрей остальных (выполняет меньше действий, но проходит все тесты).

## Тестирование решений

1. Поместить все решения в ```solutions```
1. Поправить метод ```Solution#samples``` в случае необходимости
1. Запустить ```ruby tests.rb```
