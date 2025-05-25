# 📜 Типы данных в Python

## 📌 Содержание
1. [Строки (String)](#строки-string)
2. [Логический тип данных (Bool)](#логический-тип-данных-bool)

---

## 🧱 Строки (String) 

> ❗ Индексация начинается с 0
### 🔍 Срезы строк
| Пример        | Результат   | Описание                         |
|---------------|-------------|----------------------------------|
| `s[2:5]`      | `cde`       | Символы с индексами 2-4          |
| `s[:5]`       | `abcde`     | Первые 5 символов                |
| `s[5:]`       | `fghij`     | От 5 до конца                    |
| `s[-2:]`      | `ij`        | Последние 2 символа              |
| `s[:]`        | `abcdefghij`| Вся строка                       |
| `s[1:7:2]`    | `bdf`       | Каждый второй символ от 1 до 6   |
| `s[::-1]`     | `jihgfedcba`| Обратный порядок                 |

> 🧠 **Совет**: Используйте `s[start:end:step]` для гибкой работы с подстроками.

---

### 🛠 Методы строк

#### 🔠 Конвертация регистра
| Метод         | Пример                                | Результат            |
|---------------|---------------------------------------|----------------------|
| `capitalize()`| `"foo123#BAR#." → capitalize()`       | `Foo123#bar#.`       |
| `swapcase()`  | `"FOO Bar 123 baz qUX" → swapcase()` | `foo bAR 123 BAZ Qux`|
| `title()`     | `"what's happened" → title()`         | `What'S Happened`    |
| `lower()`     | `"FOO Bar" → lower()`                | `foo bar`            |
| `upper()`     | `"foo Bar" → upper()`                | `FOO BAR`            |

#### 🔍 Поиск и замена
| Метод          | Пример                                      | Результат           |
| -------------- | ------------------------------------------- | ------------------- |
| `count()`      | `"foo goo moo".count("oo")`                 | `3`                 |
| `startswith()` | `"foobar".startswith("foo")`                | `True`              |
| `endswith()`   | `"foobar".endswith("bar")`                  | `True`              |
| `find()`       | `"bar".find("bar")`                         | `0`                 |
| `index()`      | `"asdasdasd".index("d")`                    | `2`                 |
| `replace()`    | `"foo bar foo".replace("foo", "grault", 2)` | `grault bar grault` |

> ⚠️ **Важно**: `index()` вызывает ошибку при отсутствии подстроки, `find()` возвращает `-1`.

---

#### 🧹 Удаление пробелов
| Метод         | Пример                                | Результат            |
|---------------|---------------------------------------|----------------------|
| `strip()`     | `"   abc   ".strip()`                | `abc`                |
| `lstrip()`    | `"   abc   ".lstrip()`               | `abc   `             |
| `rstrip()`    | `"   abc   ".rstrip()`               | `   abc`             |

---

#### 📊 Классификация символов
| Метод         | Проверяет                          | Пример                | Результат |
|---------------|------------------------------------|-----------------------|-----------|
| `isalnum()`   | Буквы + цифры                      | `"abc123".isalnum()` | `True`    |
| `isalpha()`   | Только буквы                        | `"ABC".isalpha()`     | `True`    |
| `isdigit()`   | Только цифры                        | `"123".isdigit()`     | `True`    |
| `islower()`   | Все буквы строчные                  | `"abc".islower()`     | `True`    |
| `isupper()`   | Все буквы заглавные                 | `"ABC".isupper()`     | `True`    |
| `isspace()`   | Только пробелы                      | `"   ".isspace()`     | `True`    |

---

#### 🧩 Форматирование строк

```python
# f-строки (рекомендуется):
name = "Alice"
print(f"Привет, {name}!")  # Привет, Alice!

# format():
text = "My name is {0}, I'm {1} years old".format("Bob", 25)
print(text) # My name is Bob, I'm 25 years old
```

#### 🧮 Разделение и объединение

```python
# split() → список:
words = "a,b,c".split(",")  # ['a', 'b', 'c']

# join() → строка:
print(" ".join(["Hello", "World"]))  # Hello World
```

## 🔍 Логический тип данных (Bool) 

### 📋 Таблица истинности

| Тип данных | Пример   | `bool()`→ результат | Пояснение                      |
| ---------- | -------- | ------------------- | ------------------------------ |
| Строка     | `''`     | `False`             | Пустая строка → False          |
|            | `'ABC'`  | `True`              | Непустая строка → True         |
| Число      | `0`      | `False`             | Ноль → False                   |
|            | `-5`     | `True`              | Любое ненулевое число → True   |
| Список     | `[]`     | `False`             | Пустой список → False          |
|            | `[1, 2]` | `True`              | Непустой список → True         |
| None       | `None`   | `False`             | Отсутствующее значение → False |
>💡 **Совет** :
> - `if flag:` вместо `if flag == True:`
> - `if not flag:` вместо `if flag == False:`

### 🧠 Функция `bool()` 

Преобразует значения других типов в булево значение.

#### 🧠 Примеры:

```python
print(bool('Beegeek'))    # True
print(bool(17))           # True
print(bool(['a', 'b']))   # True

print(bool(''))           # False
print(bool(0))            # False
print(bool([]))           # False
```

>⚠️ **Важно** :
>	- `bool()` без аргументов → `False`
>	- Если объект пустой/нулевой → `False`, иначе → `True`.

### 🧮 Функция `isinstance()`

Проверяет тип объекта.

#### 🧠 Примеры:

```python
print(isinstance(3, int))          # True
print(isinstance(3.5, float))     # True
print(isinstance('Beegeek', str)) # True
print(isinstance([1, 2], list))   # True
print(isinstance(True, bool))     # True

print(isinstance(3.5, int))      # False
print(isinstance('Beegeek', int))# False
```

>🧪 **Практическое применение** :  
	Используется для валидации входных данных:

```python
def process_data(data):
    if isinstance(data, str):
        print("Обработка строки")
    elif isinstance(data, list):
        print("Обработка списка")
```

### 📐 Логические операторы и таблицы истинности

#### Таблица истинности для `and`, `or`, `not`

| A     | B     | `A and B` | `A or B` | `not A` |
| ----- | ----- | --------- | -------- | ------- |
| False | False | False     | False    | True    |
| False | True  | False     | True     | True    |
| True  | False | False     | True     | False   |
| True  | True  | True      | True     | False   |
#### 🧠 Примеры:

```python
print(True and False)   # False
print(True or False)    # True
print(not True)         # False
```

>📝 **Правила работы `and` и `or`** :
>	- `and` возвращает **последнее значение** , если оно `False`, иначе первое `False`.
>	- `or` возвращает **первое `True`** , или последнее значение, если все `False`.

### ⚠️ Частые ошибки

| Ошибка                      | Пример                | Решение                              |
| --------------------------- | --------------------- | ------------------------------------ |
| Неправильная проверка типа  | `if type(x) == list:` | Используйте`isinstance(x, list)`     |
| Проверка числа через строку | `if num == "0":`      | Используйте`if num == 0:`            |
| Непонимание`not []`         | `if not data:`→`True` | Проверьте, что`data`не пустой список |
