# 📜 Параметры `sep` и `end` в `print()`, Циклы в Python

## 📌 Содержание

1. [Параметр `sep`](#параметр-sep)
2. [Параметр `end`](#параметр-end)
3. [Использование `sep` и `end` вместе](#использование-sep-и-end-вместе)
4. [Цикл `for`](#цикл-for)
5. [Функция `range()`](#функция-range)
6. [Цикл `while`](#цикл-while)
7. [Операторы `break` и `continue`](#операторы-break-и-continue)
## 🧰 Параметр `sep`

### 📝 Описание:

По умолчанию `sep=' '` (пробел). Указывает, какой символ или строка разделяет элементы при выводе.

### 🔁 Примеры:

```python
print('aa', 'bb', 'cc')           # aa bb cc
print('aa', 'bb', 'cc', sep='*')  # aa*bb*cc
```

>💡 Совет: используйте переменные для гибкости:

```python
delimiter = '-'
print('aa', 'bb', 'cc', sep=delimiter)  # aa-bb-cc
```

## 🚀 Параметр `end`

### 📝 Описание:

По умолчанию `end='\n'` (перевод строки). Указывает, чем заканчивается вывод.
### 🔁 Примеры:

```python
print("Hello", end='! ')
print("World")  # Hello! World
```

>🧪 Пример с переменной:

```python
suffix = '-'
print('a', 'b', 'c', end=suffix)
print('second line')  # a b c-second line
```

## 🔗 Использование `sep` и `end` вместе

### 🧠 Пример:

```python
print('a', 'b', 'c', sep='*', end='#')
# a*b*c#
```
### 📈 Сложный пример:

```python
print('a', '\n', 'b', '\n', 'c', sep='*', end='#')
# a*
# *b*
# *c#
```

## 🔁 Цикл `for`

### 📝 Синтаксис:

```python
for i in range(10):
    print('Привет')
```

### 🧮 Пример с переменной:

```python
for i in range(5):
    print("Итерация: ", i)
```

## 📏 Функция `range()`

### 📋 Таблица параметров:

| Формат                     | Описание            | Пример                     |
| -------------------------- | ------------------- | -------------------------- |
| `range(stop)`              | От 0 до`stop-1`     | `range(3)`→ 0,1,2          |
| `range(start, stop)`       | От`start`до`stop-1` | `range(2,5)`→ 2,3,4        |
| `range(start, stop, step)` | С шагом`step`       | `range(1,10,2)`→ 1,3,5,7,9 |
### 📉 Пример с отрицательным шагом:

```python
for i in range(5, 0, -1):
    print(i, end=' ')  # 5 4 3 2 1
```

## ⏳ Цикл `while`

### 📝 Синтаксис:

```python
i = 0
while i < 10:
    print('Привет')
    i += 1
```

### 🔁 Пример с вводом:

```python
num = int(input())
while num != -1:
    print('Квадрат:', num * num)
    num = int(input())
```

## 🔒 Операторы `break` и `continue`
### 📋 Таблица:

| Оператор   | Действие            | Пример                    |
| ---------- | ------------------- | ------------------------- |
| `break`    | Прерывает цикл      | Проверка на простое число |
| `continue` | Пропускает итерацию | Пропуск чисел 7,17,29,78  |
### 🧪 Пример с `break`:

```python
num = int(input())
flag = True
for i in range(2, num):
    if num % i == 0:
        flag = False
        break
        
if flag == True:
	print('Число простое')
else:
	print('Число составное')
```

> 💡 **Пояснение**: `flag` используется для проверки, является ли число простым. Если делитель найден, флаг меняется на `False`.

### 🧪 Пример с `continue`:

```python
for i in range(1, 101):
    if i in [7, 17, 29, 78]:
        continue
    print(i)
```

## 📚 Полезные ссылки

`Визуализация простого кода` -- [PythonTutor](https://pythontutor.com/)
`Официальный стандарт написания кода на Python` -- [PEP8](https://pythonworld.ru/osnovy/pep-8-rukovodstvo-po-napisaniyu-koda-na-python.html)