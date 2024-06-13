# Строки (Strings)

## Кавычки

- Разницы в одиночных и двойных кавычках нет
- Можно использовать кавычки внутри пары кавычек другого типа

```python
print("It's alright")
print("He is called 'Johnny'")
print('He is called "Johnny"')
```

- Либо можно экранировать кавычки обратным слэшем (про остальное экранирование позже)

```python
print("He is called \"Johnny\"")
print('He is called \'Johnny\'')
```

- Также тройным символом кавычки можно создать многострочный string

```python
"""Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."""
```

```python
'''Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua.'''
```

## Методы для работы со строками

### Длина строки — `len()`

```python
a = "Hello, World!"
print(len(a)) # => 13
```

### Проверка вхождения одной строки в другую — `str in str`

```python
txt = "The best things in life are free!"
print("free" in txt) # => True
print("free" not in txt) # => False
```

### Другие методы
```python
"Hello, World!".upper() # => 'HELLO, WORLD!'

"Hello, World!".lower() # => 'hello, world!'

" Hello, World! ".strip() # => 'Hello, World!'

"Pupa".replace("P", "L") # => 'Lupa'

"Ivan Ivanov".split(" ") # => ['Ivan', 'Ivanov']

"hello".capitalize() # => 'Hello' (Converts the first character to upper case)

"SOME@EMAIL.COM".casefold() # => 'some@email.com' (Converts string into lower case)

'asdf'.center(20) # => '        asdf        ' (Returns a centered string)

'hello world'.count('o') # => 2 (Returns the number of times a specified value occurs in a string)

'My name is Ståle'.encode() # => b'My name is St\xc3\xa5le' (Returns an encoded version of the string)

'hello'.endswith('lo') # => True (Returns true if the string ends with the specified value)

'\thello'.expandtabs(2) # => '  hello' (Sets the tab size of the string)

'hello'.find('e') # => 1 (Searches the string for a specified value and returns the position of where it was found)

'hello'.index('e') # => '1' (Searches the string for a specified value and returns the position of where it was found)

'My name is {} and I am {} years old.'.format('Alice', 30) # => 'My name is Alice and I am 30 years old.' (Formats specified values in a string)

'My name is {name} and I am {age} years old.'.format_map({'name': 'Alice', 'age': 30}) # => 'My name is Alice and I am 30 years old.' (Formats specified values in a string)

'Hello123'.isalnum() # => 'True' (Returns True if all characters in the string are alphanumeric)

'Hello'.isalpha() # => 'True' (Returns True if all characters in the string are in the alphabet)

'Hello'.isascii() # => 'True' (Returns True if all characters in the string are ascii characters)

'12345'.isdecimal() # => 'True' (Returns True if all characters in the string are decimals)

'12345'.isdigit() # => 'True' (Returns True if all characters in the string are digits)

'12345'.isnumeric() # => 'True' (Returns True if all characters in the string are numeric)

'variable_name'.isidentifier() # => 'True' (Returns True if the string is an identifier)

'hello'.islower() # => 'True' (Returns True if all characters in the string are lower case)

'Hello, world!'.isprintable() # => 'True' (Returns True if all characters in the string are printable)

'   '.isspace() # => 'True' (Returns True if all characters in the string are whitespaces)

'Hello World'.istitle() # => 'True' (Returns True if the string follows the rules of a title)

'HELLO'.isupper() # => 'True' (Returns True if all characters in the string are upper case)

', '.join(['apple', 'banana', 'cherry']) # => 'apple, banana, cherry' (Joins the elements of an iterable to the end of the string)

'Hello'.ljust(10, '*') # => 'Hello*****' (Returns a left justified version of the string)

'   Hello'.lstrip() # => 'Hello' (Returns a left trim version of the string)

'hello'.translate(str.maketrans('aeiou', '12345')) # => 'h2ll4' (Returns a translation table to be used in translations)

'Hello, world!'.partition(', ') # => ('Hello', ', ', 'world!') (Returns a tuple where the string is parted into three parts)

'Hello, world!'.replace('world', 'there') # => 'Hello, there!' (Returns a string where a specified value is replaced with a specified value)

'Hello, world! Hello, everyone!'.rfind('Hello') # => '14' (Searches the string for a specified value and returns the last position of where it was found)

'Hello, world! Hello, everyone!'.rindex('Hello') # => '14' (Searches the string for a specified value and returns the last position of where it was found)

'Hello'.rjust(10, '*') # => '*****Hello' (Returns a right justified version of the string)

'Hello, world! Hello, everyone!'.rpartition('Hello') # => ('Hello, world! ', 'Hello', ', everyone!') (Returns a tuple where the string is parted into three parts)

'Hello   '.rstrip() # => 'Hello' (Returns a right trim version of the string)

'a b c d'.split(' ', 2) # => ['a', 'b', 'c d']

'a b c d'.rsplit(' ', 2) # => ['a b', 'c', 'd']

'Hello\nWorld\nWelcome'.splitlines() # => ['Hello', 'World', 'Welcome'] (Splits the string at line breaks and returns a list)

'Hello, world!'.startswith('Hello') # => 'True' (Returns true if the string starts with the specified value)

'Hello, World!'.swapcase() # => 'hELLO, wORLD!' (Swaps cases, lower case becomes upper case and vice versa)

'hello world'.title() # => 'Hello World' (Converts the first character of each word to upper case)

'42'.zfill(5) # => '00042' (Fills the string with a specified number of 0 values at the beginning)
```

### Конкатенация и форматирование строк

Для обычной конкатенации строк используется оператор `+`:

```python
a = "Hello"
b = "World"

a + b # => 'HelloWorld'
a + ' ' + b # => 'Hello World'
```

Для форматирования строк используются F-строки:
```python
age = 36
f"My name is John, I am {age}" # => 'My name is John, I am 36'
```

Необязательно использовать какую-то переменную для того, чтобы использовать её в строке. Также возможно использовать любое выражение:
```python
f"The price is {20 * 59} dollars" => # 'The price is 1180 dollars'

def name():
    return 'Pupa'

f"Hello, my name is {name()}" # => 'Hello, my name is Pupa'
```

Также есть модификаторы (modifier) могут изменять вставляемое в строку значение. Они указываются через символ `:`, к примеру `:.2f`, который фиксирует количество знаков после запятой:

```python
f"The price is {69:.2f} dollars" # => 'The price is 69.00 dollars'
f"The price is {69.1234:.2f} dollars" # => 'The price is 69.12 dollars'
```

(Другие модификаторы)[https://learnpython.com/blog/python-string-formatting/]

Любое выражение, используемое в форматировании строки, будет конвертировано в строку:

```python
class Foo:
    def __str__(self):
        return 'foo'

f = Foo()
f"hello {f}" # => 'hello foo'
```

## String - массив

В python строки имеют некоторые операции, схожие с операциями на массивах

Получение символа по его индексу в строке:
```python
a = "Hello, World!"
print(a[0]) # => 'H'
print(a[1]) # => 'e'
```

Итерирование по строке в цикле:
```python
for x in 'banana':
    print(x)
```

### Slicing Strings

Python предоставляет возможность получить подстроку при указании индексов начального и конечного символа (первый символ строки имеет индекс 0)

!! Конечный символ не включается в подстроку !!

```python
"abcdef"[3:5] # => 'de'
```

Если опустить начальный индекс подстроки, то автоматически будет использоваться первый символ строки.
Точно так же, если опустить конечный индекс, автоматически будет выбран последний символ строки:

```python
"abcdef"[:5] # => 'abcde'
"abcdef"[3:] # => 'def'
"abcdef"[:] # => 'abcdef' (lol)
```

Можно использовать отрицательные индексы, чтобы выбрать подстроку с конца строки:

```python
"abcdef"[-5:-2] # => 'bcd'
```

В этом случае, последний символ имеет индекс -1. Точно так же, как и раньше, символ с индексом -2 не включён в подстроку.

Приколы:
```python
"abcdef"[-5:0] # => ''
"abcdef"[3:1] # => ''

"abcdef"[1:-3] # => 'bc'
"abcdef"[-4:4] # => 'cd'
```

## Экранирование символов

Используется для того, чтобы некоторые отображать некоторые символы как они есть (кавычки и слеш), а так же для использования специальных символов

```python
\’	Single Quote
\”	Double Quote
\\	Backslash
\n	New Line
\r	Carriage Retrun (for electromechanical teletype-like "terminals", \r commands the carriage to go back leftwards until it hits the leftmost stop)
\t	Tab
\b	Backspace
\f	Form Feed (It skips to the start of the next page. Applies mostly to terminals where the output device is a printer rather than a VDU.)
\ooo	Octal Value
\xhh	Hex Value
```
