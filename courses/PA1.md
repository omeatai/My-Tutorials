### [A1-PYTHON TUTORIAL - W3SCHOOLS](/courses/A1.md)

<details>
  <summary>1. Introduction </summary>

# Check python version

<details>
  <summary>Solution </summary>

```py
python --version
```

</details>

# Print out value

<details>
  <summary>Solution </summary>

```py
print("Hello, World!")
```

</details>

# Python Comments

<details>
  <summary>Solution </summary>

```py
#This is a comment
print("Hello, World!")
```

```py
#This is a comment
#written in
#more than just one line
print("Hello, World!")
```

```py
"""
This is a comment
written in
more than just one line
"""
print("Hello, World!")
```

</details>

# Python Variables

<details>
  <summary>Solution </summary>

```py
x = 5
y = "John"
print(x)
print(y)
```

```py
# 5
# John
```

</details>

# Type Casting

<details>
  <summary>Solution </summary>

```py
x = str(3)    # x will be '3'
y = int(3)    # y will be 3
z = float(3)  # z will be 3.0
```

```py
# 3
# 3
# 3.0
```

</details>

# Get Data Type

<details>
  <summary>Solution </summary>

```py
x = 5
y = "John"
print(type(x))
print(type(y))
```

```py
# <class 'int'>
# <class 'str'>
```

</details>

</details>

<details>
  <summary>2. Many Values to Multiple Variables </summary>

# Many Values to Multiple Variables

```py
x, y, z = "Orange", "Banana", "Cherry"
print(x)
print(y)
print(z)
```

```py
# Orange
# Banana
# Cherry
```

</details>

<details>
  <summary>3. One Value to Multiple Variables </summary>

# One Value to Multiple Variables

```py
x = y = z = "Orange"
print(x)
print(y)
print(z)
```

```py
# Orange
# Orange
# Orange
```

</details>

<details>
  <summary>4. Unpacking a Collection </summary>

# Unpacking a Collection

```py
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x)
print(y)
print(z)
```

```py
# apple
# banana
# cherry
```

</details>

<details>
  <summary>5. Outputing Variables </summary>

# Outputing Variables

```py
x = "Python"
y = "is"
z = "awesome"
print(x, y, z)
```

```py
# Python is awesome
```

```py
x = "Python "
y = "is "
z = "awesome"
print(x + y + z)
```

```py
# Python is awesome
```

</details>

<details>
  <summary>6. Global Variables </summary>

# Global Variables

```py
x = "awesome"

def myfunc():
  print("Python is " + x)

myfunc()
```

```py
# Python is awesome
```

</details>

<details>
  <summary>7. Local Variable </summary>

# Local Variable

```py
x = "awesome"

def myfunc():
  x = "fantastic"
  print("Python is " + x)

myfunc()

print("Python is " + x)
```

```py
# Python is fantastic
# Python is awesome
```

</details>

<details>
  <summary>8. The global Keyword</summary>

# The global Keyword

```py
x = "awesome"

def myfunc():
  global x
  x = "fantastic"

myfunc()

print("Python is " + x)
```

```py
# Python is fantastic
```

</details>

<details>
  <summary>9. Python Data Types </summary>

# Built-in Data Types

```py
Text Type:	    str
Numeric Types:	int, float, complex
Sequence Types:	list, tuple, range
Mapping Type:	  dict
Set Types:	    set, frozenset
Boolean Type:	  bool
Binary Types:	  bytes, bytearray, memoryview
None Type:	    NoneType
```

# Get Data Type

```py
x = 5
print(type(x))
```

```py
# <class 'int'>
```

# Set String Type

```py
x = "Hello World"
```

```py
x = str("Hello World")
```

# Set Integer Type

```py
x = 20
```

```py
x = int(20)
```

# Set Float Type

```py
x = 20.5
```

```py
x = float(20.5)
```

# Set Complex Type

```py
x = 1j
```

```py
x = complex(1j)
```

# Set List Type

```py
x = ["apple", "banana", "cherry"]
```

```py
x = list(("apple", "banana", "cherry"))
```

# Set Tuple Type

```py
x = ("apple", "banana", "cherry")
```

```py
x = tuple(("apple", "banana", "cherry"))
```

# Set Range Type

```py
x = range(6)
```

# Set Dictionary Type

```py
x = {"name" : "John", "age" : 36}
```

```py
x = dict(name="John", age=36)
```

# Set Set Type

```py
x = {"apple", "banana", "cherry"}
```

```py
x = set(("apple", "banana", "cherry"))
```

# Set FrozenSet Type

```py
x = frozenset({"apple", "banana", "cherry"})
```

```py
x = frozenset(("apple", "banana", "cherry"))
```

# Set Bool Type

```py
x = True
```

```py
x = bool(5)
```

# Set Bytes Type

```py
x = b"Hello"
```

```py
x = bytes(5)
```

# Set ByteArray Type

```py
x = bytearray(5)
```

# Set Memoryview Type

```py
x = memoryview(bytes(5))
```

# Set None Type

```py
x = None
```

</details>

+STRINGS

<details>
  <summary>10. Python Strings </summary>

- Strings in python are surrounded by either single quotation marks, or double quotation marks.

- 'hello' is the same as "hello".

- You can display a string literal with the print() function.

- Assigning a string to a variable is done with the variable name followed by an equal sign and the string.

- You can assign a multiline string to a variable by using three quotes.

- Square brackets can be used to access elements of the string.

```py
print("Hello")
print('Hello')
```

```py
a = "Hello"
print(a)
```

```py
a = """Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."""
print(a)
```

```py
a = '''Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua.'''
print(a)
```

```py
# Lorem ipsum dolor sit amet,
# consectetur adipiscing elit,
# sed do eiusmod tempor incididunt
# ut labore et dolore magna aliqua.
```

```py
a = "Hello, World!"
print(a[1])
```

```py
# e
```

</details>

<details>
  <summary>11. Python Strings - Looping </summary>

- Since strings are arrays, we can loop through the characters in a string, with a for loop.

```py
for x in "banana":
  print(x)
```

```py
# b
# a
# n
# a
# n
# a
```

</details>

<details>
  <summary>12. Python Strings - Length </summary>

- To get the length of a string, use the len() function.

```py
a = "Hello, World!"
print(len(a))
```

```py
# 13
```

</details>

<details>
  <summary>13. Python Strings - Check in String </summary>

- To check if a certain phrase or character is present in a string, we can use the keyword in.

```py
txt = "The best things in life are free!"
print("free" in txt)
```

```py
# True
```

```py
txt = "The best things in life are free!"
if "free" in txt:
  print("Yes, 'free' is present.")
```

```py
# Yes, 'free' is present.
```

</details>

<details>
  <summary>14. Python Strings - Check not in String </summary>

```py
txt = "The best things in life are free!"
print("expensive" not in txt)
```

```py
# True
```

```py
txt = "The best things in life are free!"
if "expensive" not in txt:
  print("No, 'expensive' is NOT present.")
```

```py
# No, 'expensive' is NOT present.
```

</details>

<details>
  <summary>15. Python Strings - Slicing Strings </summary>

- You can return a range of characters by using the slice syntax.

- Specify the start index and the end index, separated by a colon, to return a part of the string.

- By leaving out the start index, the range will start at the first character.

- By leaving out the end index, the range will go to the end.

- Use negative indexes to start the slice from the end of the string.

```py
b = "Hello, World!"
print(b[2:5])
```

```py
# llo
```

```py
b = "Hello, World!"
print(b[:5])
```

```py
# Hello
```

```py
b = "Hello, World!"
print(b[2:])
```

```py
# llo, World!
```

```py
b = "Hello, World!"
print(b[-5:-2])
```

```py
# orl
```

</details>

<details>
  <summary>16. Python Strings - Upper and Lower Case </summary>

- The upper() method returns the string in upper case.

- The lower() method returns the string in lower case.

```py
a = "Hello, World!"
print(a.upper())
```

```py
# HELLO, WORLD!
```

```py
a = "Hello, World!"
print(a.lower())
```

```py
# hello, world!
```

</details>

<details>
  <summary>17. Python Strings - Strip (Remove) Whitespace</summary>

- Whitespace is the space before and/or after the actual text, and very often you want to remove this space.

- The strip() method removes any whitespace from the beginning or the end

```py
a = " Hello, World! "
print(a.strip()) # returns "Hello, World!"
```

```py
# Hello, World!
```

</details>

<details>
  <summary>18. Python Strings - Replace String </summary>

- The replace() method replaces a string with another string.

```py
a = "Hello, World!"
print(a.replace("H", "J"))
```

```py
# Jello, World!
```

</details>

<details>
  <summary>19. Python Strings - Split String </summary>

- The split() method returns a list where the text between the specified separator becomes the list items.

- The split() method splits the string into substrings if it finds instances of the separator.

```py
a = "Hello, World!"
print(a.split(",")) # returns ['Hello', ' World!']
```

```py
# ['Hello', ' World!']
```

</details>

<details>
  <summary>20. Python Strings - String Concatenation </summary>

- To concatenate, or combine, two strings you can use the + operator.

```py
a = "Hello"
b = "World"
c = a + b
print(c)
```

```py
# HelloWorld
```

```py
a = "Hello"
b = "World"
c = a + " " + b
print(c)
```

```py
# Hello World
```

</details>

<details>
  <summary>21. Python Strings - Format Strings </summary>

- We can combine strings and numbers by using the format() method!

- The format() method takes the passed arguments, formats them, and places them in the string where the placeholders {} are.

- The format() method takes unlimited number of arguments, and are placed into the respective placeholders.

- You can use index numbers {0} to be sure the arguments are placed in the correct placeholders.

```py
age = 36
txt = "My name is John, and I am {}"
print(txt.format(age))
```

```py
# My name is John, and I am 36
```

```py
quantity = 3
itemno = 567
price = 49.95
myorder = "I want {} pieces of item {} for {} dollars."
print(myorder.format(quantity, itemno, price))
```

```py
# I want 3 pieces of item 567 for 49.95 dollars.
```

```py
quantity = 3
itemno = 567
price = 49.95
myorder = "I want to pay {2} dollars for {0} pieces of item {1}."
print(myorder.format(quantity, itemno, price))
```

```py
# I want to pay 49.95 dollars for 3 pieces of item 567
```

</details>

<details>
  <summary>22. Python Strings - Escape Characters </summary>

- To insert characters that are illegal in a string, use an escape character.

- An escape character is a backslash \ followed by the character you want to insert.

- An example of an illegal character is a double quote inside a string that is surrounded by double quotes. To fix this problem, use the escape character \".

```py
txt = "We are the so-called \"Vikings\" from the north."
```

```py
# We are the so-called "Vikings" from the north.
```

```bs
\'	  Single Quote
\\	  Backslash
\n	  New Line
\r	  Carriage Return
\t	  Tab
\b	  Backspace
\f	  Form Feed
\ooo	  Octal value
\xhh	  Hex value
```

</details>

<details>
  <summary>23. Python Strings - capitalize() Method</summary>

- The capitalize() method returns a string where the first character is upper case, and the rest is lower case.

```bs
string.capitalize()
```

```py
txt = "hello, and welcome to my world."

x = txt.capitalize()

print (x)
```

```py
# Hello, and welcome to my world.
```

```py
txt = "python is FUN!"

x = txt.capitalize()

print (x)
```

```py
# Python is fun!
```

```py
txt = "36 is my age."

x = txt.capitalize()

print (x)
```

```py
# 36 is my age
```

</details>

<details>
  <summary>24. Python Strings - casefold() Method </summary>

- The casefold() method returns a string where all the characters are lower case.

- This method is similar to the lower() method, but the casefold() method is stronger, more aggressive, meaning that it will convert more characters into lower case, and will find more matches when comparing two strings and both are converted using the casefold() method.

```py
txt = "Hello, And Welcome To My World!"

x = txt.casefold()

print(x)
```

```py
# hello, and welcome to my world!
```

</details>

<details>
  <summary>25. Python Strings - center() Method </summary>

- The center() method will center align the string, using a specified character (space is default) as the fill character.

```bs
string.center(length, character)
```

```py
txt = "banana"

x = txt.center(20)

print(x)
```

```py
# "    banana     "
```

```py
txt = "banana"

x = txt.center(20, "O")

print(x)
```

```py
# OOOOOOObananaOOOOOOO
```

</details>

<details>
  <summary>26. Python Strings - count() Method </summary>

- The count() method returns the number of times a specified value appears in the string.

```bs
string.count(value, start, end)
```

```py
txt = "I love apples, apple are my favorite fruit"

x = txt.count("apple")

print(x)
```

```py
# 2
```

```py
txt = "I love apples, apple are my favorite fruit"

x = txt.count("apple", 10, 24)

print(x)
```

```py
# 1
```

</details>

<details>
  <summary>27. Python Strings - encode() Method </summary>

- The encode() method encodes the string, using the specified encoding. If no encoding is specified, UTF-8 will be used.

```bs
string.encode(encoding=encoding, errors=errors)
```

```py
txt = "My name is Ståle"

x = txt.encode()

print(x)
```

```py
# b'My name is St\xc3\xe5le'
```

```py
txt = "My name is Ståle"

print(txt.encode(encoding="ascii",errors="backslashreplace"))
print(txt.encode(encoding="ascii",errors="ignore"))
print(txt.encode(encoding="ascii",errors="namereplace"))
print(txt.encode(encoding="ascii",errors="replace"))
print(txt.encode(encoding="ascii",errors="xmlcharrefreplace"))
```

```py
# b'My name is St\\xe5le'
# b'My name is Stle'
# b'My name is St\\N{LATIN SMALL LETTER A WITH RING ABOVE}le'
# b'My name is St?le'
# b'My name is Ståle'
```

</details>

<details>
  <summary>28. Python Strings - endswith() Method </summary>

- The endswith() method returns True if the string ends with the specified value, otherwise False.

```bs
string.endswith(value, start, end)
```

```py
txt = "Hello, welcome to my world."

x = txt.endswith(".")

print(x)
```

```py
# True
```

```py
txt = "Hello, welcome to my world."

x = txt.endswith("my world.")

print(x)
```

```py
# True
```

```py
txt = "Hello, welcome to my world."

x = txt.endswith("my world.", 5, 11)

print(x)
```

```py
# False
```

</details>

<details>
  <summary>29. Python Strings - expandtabs() Method </summary>

- The expandtabs() method sets the tab size to the specified number of whitespaces.

```bs
string.expandtabs(tabsize)
```

```py
txt = "H\te\tl\tl\to"

x =  txt.expandtabs(2)

print(x)
```

```py
# H e l l o
```

```py
txt = "H\te\tl\tl\to"

print(txt)
print(txt.expandtabs())
print(txt.expandtabs(2))
print(txt.expandtabs(4))
print(txt.expandtabs(10))
```

```py
# H       e       l       l       o
# H       e       l       l       o
# H e l l o
# H   e   l   l   o
# H         e         l         l         o
```

</details>

<details>
  <summary>30. Python Strings - find() Method </summary>

- The find() method finds the first occurrence of the specified value.

- The find() method returns -1 if the value is not found.

- The find() method is almost the same as the index() method, the only difference is that the index() method raises an exception if the value is not found.

```bs
string.find(value, start, end)
```

```py
txt = "Hello, welcome to my world."

x = txt.find("welcome")

print(x)
```

```py
# 7
```

```py
txt = "Hello, welcome to my world."

x = txt.find("e")

print(x)
```

```py
# 1
```

```py
txt = "Hello, welcome to my world."

x = txt.find("e", 5, 10)

print(x)
```

```py
# 8
```

```py
txt = "Hello, welcome to my world."

print(txt.find("q"))
print(txt.index("q"))
```

```py
# -1
# Traceback (most recent call last):
#   File "demo_ref_string_find_vs_index.py", line 4 in <module>
#     print(txt.index("q"))
# ValueError: substring not found
```

</details>

<details>
  <summary>31. Python Strings - format() Method </summary>

- The format() method formats the specified value(s) and insert them inside the string's placeholder.

- The placeholder is defined using curly brackets: {}.

- The format() method returns the formatted string.

- The placeholders can be identified using named indexes {price}, numbered indexes {0}, or even empty placeholders {}.

```bs
string.format(value1, value2...)
```

```py
txt = "For only {price:.2f} dollars!"
print(txt.format(price = 49))
```

```py
# For only 49.00 dollars!
```

```py
txt1 = "My name is {fname}, I'm {age}".format(fname = "John", age = 36)
txt2 = "My name is {0}, I'm {1}".format("John",36)
txt3 = "My name is {}, I'm {}".format("John",36)
```

```py
# My name is John, I'm 36
# My name is John, I'm 36
# My name is John, I'm 36
```

</details>

<details>
  <summary>32. Python Strings - index() Method </summary>

- The index() method finds the first occurrence of the specified value.

- The index() method raises an exception if the value is not found.

- The index() method is almost the same as the find() method, the only difference is that the find() method returns -1 if the value is not found.

```bs
string.index(value, start, end)
```

```py
txt = "Hello, welcome to my world."

x = txt.index("welcome")

print(x)
```

```py
# 7
```

```py
txt = "Hello, welcome to my world."

x = txt.index("e")

print(x)
```

```py
# 1
```

```py
txt = "Hello, welcome to my world."

x = txt.index("e", 5, 10)

print(x)
```

```py
# 8
```

```py
txt = "Hello, welcome to my world."

print(txt.find("q"))
print(txt.index("q"))
```

```py
# -1
# Traceback (most recent call last):
#   File "demo_ref_string_find_vs_index.py", line 4 in <module>
#     print(txt.index("q"))
# ValueError: substring not found
```

</details>

<details>
  <summary>33. Python Strings - isalnum() Method </summary>

- The isalnum() method returns True if all the characters are alphanumeric, meaning alphabet letter (a-z) and numbers (0-9).

- Example of characters that are not alphanumeric: (space)!#%&? etc.

```bs
string.isalnum()
```

```py
txt = "Company12"

x = txt.isalnum()

print(x)
```

```py
# True
```

```py
txt = "Company 12"

x = txt.isalnum()

print(x)
```

```py
# False
```

</details>

<details>
  <summary>34. Python Strings - isalpha() Method </summary>

- The isalpha() method returns True if all the characters are alphabet letters (a-z).

- Example of characters that are not alphabet letters: (space)!#%&? etc.

```py
txt = "CompanyX"

x = txt.isalpha()

print(x)

```

```py
# True
```

```py
txt = "Company10"

x = txt.isalpha()

print(x)

```

```py
# False
```

</details>

<details>
  <summary>35. Python Strings - isdecimal() Method </summary>

- The isdecimal() method returns True if all the characters are decimals (0-9).

- This method is used on unicode objects.

```py
a = "\u0030" #unicode for 0
b = "\u0047" #unicode for G

print(a.isdecimal())
print(b.isdecimal())
```

```py
# True
# False
```

</details>

<details>
  <summary>36. Python Strings - isdigit() Method </summary>

- The isdigit() method returns True if all the characters are digits, otherwise False.

- Exponents, like ², are also considered to be a digit.

```py
txt = "50800"

x = txt.isdigit()

print(x)
```

```py
# True
```

```py
a = "\u0030" #unicode for 0
b = "\u00B2" #unicode for ²

print(a.isdigit())
print(b.isdigit())
```

```py
# True
# True
```

</details>

<details>
  <summary>37. Python Strings - isidentifier() Method </summary>

- The isidentifier() method returns True if the string is a valid identifier, otherwise False.

- A string is considered a valid identifier if it only contains alphanumeric letters (a-z) and (0-9), or underscores (\_).

- A valid identifier cannot start with a number, or contain any spaces.

```py
txt = "Demo"

x = txt.isidentifier()

print(x)
```

```py
# True
```

```py
a = "MyFolder"
b = "Demo002"
c = "2bring"
d = "my demo"

print(a.isidentifier())
print(b.isidentifier())
print(c.isidentifier())
print(d.isidentifier())
```

```py
# True
# True
# False
# False
```

</details>

<details>
  <summary>38. Python Strings - islower() Method </summary>

- The islower() method returns True if all the characters are in lower case, otherwise False.

- Numbers, symbols and spaces are not checked, only alphabet characters.

```py
txt = "hello world!"

x = txt.islower()

print(x)
```

```py
# True
```

```py
a = "Hello world!"
b = "hello 123"
c = "mynameisPeter"

print(a.islower())
print(b.islower())
print(c.islower())

```

```py
# False
# True
# False
```

</details>

<details>
  <summary>39. Python Strings - isnumeric() Method  </summary>

- The isnumeric() method returns True if all the characters are numeric (0-9), otherwise False.

- Exponents, like ² and ¾ are also considered to be numeric values.

- "-1" and "1.5" are NOT considered numeric values, because all the characters in the string must be numeric, and the - and the . are not.

```py
txt = "565543"

x = txt.isnumeric()

print(x)

```

```py
# True
```

```py
a = "\u0030" #unicode for 0
b = "\u00B2" #unicode for ²
c = "10km2"
d = "-1"
e = "1.5"

print(a.isnumeric())
print(b.isnumeric())
print(c.isnumeric())
print(d.isnumeric())
print(e.isnumeric())

```

```py
# True
# True
# False
# False
# False
```

</details>

<details>
  <summary>40. Python Strings - isprintable() Method </summary>

- The isprintable() method returns True if all the characters are printable, otherwise False.

- Example of none printable character can be carriage return and line feed.

```py
txt = "Hello! Are you #1?"

x = txt.isprintable()

print(x)

```

```py
# True
```

```py
txt = "Hello!\nAre you #1?"

x = txt.isprintable()

print(x)
```

```py
# False
```

</details>

<details>
  <summary>41. Python Strings - isspace() Method  </summary>

The isspace() method returns True if all the characters in a string are whitespaces, otherwise False.

```py
txt = "   "

x = txt.isspace()

print(x)
```

```py
# True
```

```py
txt = "   s   "

x = txt.isspace()

print(x)

```

```py
# False
```

</details>

<details>
  <summary>42. Python Strings - istitle() Method </summary>

- The istitle() method returns True if all words in a text start with a upper case letter, AND the rest of the word are lower case letters, otherwise False.

- Symbols and numbers are ignored.

```py
txt = "Hello, And Welcome To My World!"

x = txt.istitle()

print(x)

```

```py
# True
```

```py
a = "HELLO, AND WELCOME TO MY WORLD"
b = "Hello"
c = "22 Names"
d = "This Is %'!?"

print(a.istitle())
print(b.istitle())
print(c.istitle())
print(d.istitle())

```

```py
# False
# True
# True
# True
```

</details>

<details>
  <summary>43. Python Strings - isupper() Method  </summary>

- The isupper() method returns True if all the characters are in upper case, otherwise False.

- Numbers, symbols and spaces are not checked, only alphabet characters.

```py
txt = "THIS IS NOW!"

x = txt.isupper()

print(x)

```

```py
# True
```

```py
a = "Hello World!"
b = "hello 123"
c = "MY NAME IS PETER"

print(a.isupper())
print(b.isupper())
print(c.isupper())

```

```py
# False
# False
# True
```

</details>

<details>
  <summary>44. Python Strings - join() Method  </summary>

- The join() method takes all items in an iterable and joins them into one string.

- A string must be specified as the separator.

```py
myTuple = ("John", "Peter", "Vicky")

x = "#".join(myTuple)

print(x)
```

```py
# John#Peter#Vicky
```

```py
myDict = {"name": "John", "country": "Norway"}
mySeparator = "TEST"

x = mySeparator.join(myDict)

print(x)

```

```py
# nameTESTcountry
```

</details>

<details>
  <summary>45. Python Strings - ljust() Method </summary>

The ljust() method will left align the string, using a specified character (space is default) as the fill character.

```py
txt = "banana"

x = txt.ljust(20)

print(x, "is my favorite fruit.")
```

```py
# banana              is my favorite fruit.
```

```py
txt = "banana"

x = txt.ljust(20, "O")

print(x)

```

```py
# bananaOOOOOOOOOOOOOO
```

</details>

<details>
  <summary>46. Python Strings - lower() Method </summary>

- The lower() method returns a string where all characters are lower case.

- Symbols and Numbers are ignored.

```py
txt = "Hello my FRIENDS"

x = txt.lower()

print(x)

```

```py
# hello my friends
```

</details>

<details>
  <summary>47. Python Strings - lstrip() Method </summary>

The lstrip() method removes any leading characters (space is the default leading character to remove).

```py
txt = "     banana     "

x = txt.lstrip()

print("of all fruits", x, "is my favorite")
```

```py
# of all fruits banana     is my favorite
```

```py
txt = ",,,,,ssaaww.....banana"

x = txt.lstrip(",.asw")

print(x)

```

```py
# banana
```

</details>

<details>
  <summary>48. Python Strings - maketrans() Method </summary>

- The maketrans() method returns a mapping table that can be used with the translate() method to replace specified characters.

```py
txt = "Hello Sam!"

mytable = txt.maketrans("S", "P")

print(txt.translate(mytable))

```

```py
# Hello Pam!
```

```py
txt = "Hi Sam!"

x = "mSa"
y = "eJo"

mytable = txt.maketrans(x, y)

print(txt.translate(mytable))

```

```py
# Hi Joe!
```

```py
txt = "Good night Sam!"

x = "mSa"
y = "eJo"
z = "odnght"

mytable = txt.maketrans(x, y, z)

print(txt.translate(mytable))
```

```py
# G i Joe!
```

</details>

<details>
  <summary>49. Python Strings - partition() Method </summary>

- The partition() method searches for a specified string, and splits the string into a tuple containing three elements.

- The first element contains the part before the specified string.

- The second element contains the specified string.

- The third element contains the part after the string.

```py
txt = "I could eat bananas all day"

x = txt.partition("bananas")

print(x)

```

```py
# ('I could eat ', 'bananas', ' all day')
```

```py
txt = "I could eat bananas all day"

x = txt.partition("apples")

print(x)

```

```py
# ('I could eat bananas all day', '', '')
```

</details>

<details>
  <summary>50. Python Strings - replace() Method </summary>

The replace() method replaces a specified phrase with another specified phrase.

```py
txt = "I like bananas"

x = txt.replace("bananas", "apples")

print(x)
```

```py
# I like apples
```

```py
txt = "one one was a race horse, two two was one too."

x = txt.replace("one", "three")

print(x)

```

```py
# three three was a race horse, two two was three too."
```

```py
txt = "one one was a race horse, two two was one too."

x = txt.replace("one", "three", 2)

print(x)

```

```py
# three three was a race horse, two two was one too."
```

</details>

<details>
  <summary>51. Python Strings - rfind() Method </summary>

- The rfind() method finds the last occurrence of the specified value.

- The rfind() method returns -1 if the value is not found.

- The rfind() method is almost the same as the rindex() method.

```py
txt = "Mi casa, su casa."

x = txt.rfind("casa")

print(x)

```

```py
# 12
```

```py
txt = "Hello, welcome to my world."

x = txt.rfind("e")

print(x)

```

```py
# 13
```

```py
txt = "Hello, welcome to my world."

x = txt.rfind("e", 5, 10)

print(x)

```

```py
# 8
```

```py
txt = "Hello, welcome to my world."

print(txt.rfind("q"))
print(txt.rindex("q"))
```

```py
# -1
# Traceback (most recent call last):
#   File "demo_ref_string_rfind_vs_rindex.py", line 4 in <module>
#     print(txt.rindex("q"))
# ValueError: substring not found
```

</details>

<details>
  <summary>52. Python Strings - rindex() Method </summary>

- The rindex() method finds the last occurrence of the specified value.

- The rindex() method raises an exception if the value is not found.

- The rindex() method is almost the same as the rfind() method.

```py
txt = "Mi casa, su casa."

x = txt.rindex("casa")

print(x)

```

```py
# 12
```

```py
txt = "Hello, welcome to my world."

x = txt.rindex("e")

print(x)

```

```py
# 13
```

```py
txt = "Hello, welcome to my world."

x = txt.rindex("e", 5, 10)

print(x)
```

```py
# 8
```

```py
txt = "Hello, welcome to my world."

print(txt.rfind("q"))
print(txt.rindex("q"))
```

```py
# -1
# Traceback (most recent call last):
#   File "demo_ref_string_rfind_vs_rindex.py", line 4 in <module>
#     print(txt.rindex("q"))
# ValueError: substring not found
```

</details>

<details>
  <summary>53. Python Strings - rjust() Method  </summary>

The rjust() method will right align the string, using a specified character (space is default) as the fill character.

```py
txt = "banana"

x = txt.rjust(20)

print(x, "is my favorite fruit.")
```

```py
#                  banana is my favorite fruit.
```

```py
txt = "banana"

x = txt.rjust(20, "O")

print(x)

```

```py
# OOOOOOOOOOOOOObanana
```

</details>

<details>
  <summary>54. Python Strings - rpartition() Method </summary>

- The rpartition() method searches for the last occurrence of a specified string, and splits the string into a tuple containing three elements.

- The first element contains the part before the specified string.

- The second element contains the specified string.

- The third element contains the part after the string.

```py
txt = "I could eat bananas all day, bananas are my favorite fruit"

x = txt.rpartition("bananas")

print(x)
```

```py
# ('I could eat bananas all day, ', 'bananas', ' are my favorite fruit')
```

```py
txt = "I could eat bananas all day, bananas are my favorite fruit"

x = txt.rpartition("apples")

print(x)
```

```py
# ('', '', 'I could eat bananas all day, bananas are my favorite fruit')
```

</details>

<details>
  <summary>55. Python Strings - rsplit() Method </summary>

- The rsplit() method splits a string into a list, starting from the right.

- If no "max" is specified, this method will return the same as the split() method.

```py
txt = "apple, banana, cherry"

x = txt.rsplit(", ")

print(x)
```

```py
# ['apple', 'banana', 'cherry']
```

```py
txt = "apple, banana, cherry"

# setting the maxsplit parameter to 1, will return a list with 2 elements!
x = txt.rsplit(", ", 1)

print(x)

# note that the result has only 2 elements "apple, banana" is the first element, and "cherry" is the last.
```

```py
['apple, banana', 'cherry']
```

</details>

<details>
  <summary>56. Python Strings - rstrip() Method </summary>

The rstrip() method removes any trailing characters (characters at the end a string), space is the default trailing character to remove.

```py
txt = "     banana     "

x = txt.rstrip()

print("of all fruits", x, "is my favorite")
```

```py
# of all fruits     banana is my favorite
```

```py
txt = "banana,,,,,ssqqqww....."

x = txt.rstrip(",.qsw")

print(x)

```

```py
# banana
```

</details>

<details>
  <summary>57. Python Strings - split() Method </summary>

```py
txt = "welcome to the jungle"

x = txt.split()

print(x)
```

```py
# ['welcome', 'to', 'the', 'jungle']
```

```py
txt = "hello, my name is Peter, I am 26 years old"

x = txt.split(", ")

print(x)
```

```py
# ['hello', 'my name is Peter', 'I am 26 years old']
```

```py
txt = "apple#banana#cherry#orange"

x = txt.split("#")

print(x)

```

```py
# ['apple', 'banana', 'cherry', 'orange']
```

```py
txt = "apple#banana#cherry#orange"

# setting the maxsplit parameter to 1, will return a list with 2 elements!
x = txt.split("#", 1)

print(x)
```

```py
# ['apple', 'banana#cherry#orange']
```

</details>

<details>
  <summary>58. Python Strings - splitlines() Method </summary>

The splitlines() method splits a string into a list. The splitting is done at line breaks.

```py
txt = "Thank you for the music\nWelcome to the jungle"

x = txt.splitlines()

print(x)

```

```py
# ['Thank you for the music', 'Welcome to the jungle']
```

```py
txt = "Thank you for the music\nWelcome to the jungle"

x = txt.splitlines(True)

print(x)

```

```py
# ['Thank you for the music\n', 'Welcome to the jungle']
```

</details>

<details>
  <summary>59. Python Strings - startswith() Method </summary>

The startswith() method returns True if the string starts with the specified value, otherwise False.

```py
txt = "Hello, welcome to my world."

x = txt.startswith("Hello")

print(x)

```

```py
# True
```

```py
txt = "Hello, welcome to my world."

x = txt.startswith("wel", 7, 20)

print(x)

```

```py
# True
```

</details>

<details>
  <summary>60. Python Strings - strip() Method </summary>

The strip() method removes any leading (spaces at the beginning) and trailing (spaces at the end) characters (space is the default leading character to remove).

```py
txt = "     banana     "

x = txt.strip()

print("of all fruits", x, "is my favorite")

```

```py
# of all fruits banana is my favorite
```

```py
txt = ",,,,,rrttgg.....banana....rrr"

x = txt.strip(",.grt")

print(x)

```

```py
# banana
```

</details>

<details>
  <summary>61. Python Strings - swapcase() Method </summary>

The swapcase() method returns a string where all the upper case letters are lower case and vice versa.

```py
txt = "Hello My Name Is PETER"

x = txt.swapcase()

print(x)

```

```py
# hELLO mY nAME iS peter
```

</details>

<details>
  <summary>62. Python Strings - title() Method </summary>

- The title() method returns a string where the first character in every word is upper case. Like a header, or a title.

- If the word contains a number or a symbol, the first letter after that will be converted to upper case.

```py
txt = "Welcome to my world"

x = txt.title()

print(x)
```

```py
# Welcome To My World
```

```py
txt = "Welcome to my 2nd world"

x = txt.title()

print(x)

```

```py
# Welcome To My 2Nd World
```

</details>

<details>
  <summary>63. Python Strings - translate() Method </summary>

- The translate() method returns a string where some specified characters are replaced with the character described in a dictionary, or in a mapping table.

- Use the maketrans() method to create a mapping table.

- If a character is not specified in the dictionary/table, the character will not be replaced.

- If you use a dictionary, you must use ascii codes instead of characters.

```py
#use a dictionary with ascii codes to replace 83 (S) with 80 (P):
mydict = {83:  80}

txt = "Hello Sam!"

print(txt.translate(mydict))

```

```py
# Hello Pam!
```

```py
txt = "Hello Sam!"

mytable = txt.maketrans("S", "P")

print(txt.translate(mytable))

```

```py
# Hello Pam!
```

```py
txt = "Hi Sam!"

x = "mSa"
y = "eJo"

mytable = txt.maketrans(x, y)

print(txt.translate(mytable))

```

```py
# Hi Joe!
```

```py
txt = "Good night Sam!"

x = "mSa"
y = "eJo"
z = "odnght"

mytable = txt.maketrans(x, y, z)

print(txt.translate(mytable))

```

```py
# G i Joe!
```

```py
txt = "Good night Sam!"

mydict = {109: 101, 83: 74, 97: 111, 111: None, 100: None, 110: None, 103: None, 104: None, 116: None}

print(txt.translate(mydict))

```

```py
# G i Joe!
```

</details>

<details>
  <summary>64. Python Strings - upper() Method </summary>

- The upper() method returns a string where all characters are in upper case.

- Symbols and Numbers are ignored.

```py
txt = "Hello my friends"

x = txt.upper()

print(x)

```

```py
# HELLO MY FRIENDS
```

</details>

<details>
  <summary>65. Python Strings - zfill() Method </summary>

- The zfill() method adds zeros (0) at the beginning of the string, until it reaches the specified length.

- If the value of the len parameter is less than the length of the string, no filling is done.

```py
txt = "50"

x = txt.zfill(10)

print(x)

```

```py
# 0000000050
```

```py
a = "hello"
b = "welcome to the jungle"
c = "10.000"

print(a.zfill(10))
print(b.zfill(10))
print(c.zfill(10))
```

```py
# 00000hello
# welcome to the jungle
# 000010.000
```

</details>

<details>
  <summary>66. Python isinstance() </summary>

Python also has many built-in functions that return a boolean value, like the isinstance() function, which can be used to determine if an object is of a certain data type

```py
x = 200
print(isinstance(x, int))
```

```py
# True
```

</details>

+LISTS

<details>
  <summary>67. Python Lists - Introduction </summary>

- Lists are used to store multiple items in a single variable.

- Lists are one of 4 built-in data types in Python used to store collections of data, the other 3 are Tuple, Set, and Dictionary, all with different qualities and usage.

- Lists are created using square brackets.

- List items are ordered, changeable, and allow duplicate values.

- List items are indexed, the first item has index [0], the second item has index [1] etc.

- The list is changeable, meaning that we can change, add, and remove items in a list after it has been created.

There are four collection data types in the Python programming language:

- List is a collection which is ordered and changeable. Allows duplicate members.
- Tuple is a collection which is ordered and unchangeable. Allows duplicate members.
- Set is a collection which is unordered, unchangeable\*, and unindexed. No duplicate members.
- Dictionary is a collection which is ordered\*\* and changeable. No duplicate members.

```py
thislist = ["apple", "banana", "cherry"]
print(thislist)
```

```py
# ['apple', 'banana', 'cherry']
```

</details>

<details>
  <summary>68. Python Lists - Length</summary>

To determine how many items a list has, use the len() function.

```py
thislist = ["apple", "banana", "cherry"]
print(len(thislist))
```

```py
# 3
```

</details>

<details>
  <summary>69. Python Lists - Data type </summary>

```py
mylist = ["apple", "banana", "cherry"]

print(type(mylist))

```

```py
# <class 'list'>
```

</details>

<details>
  <summary>70. Python Lists - list() Constructor </summary>

```py
thislist = list(("apple", "banana", "cherry"))
print(thislist)

```

```py
# ['apple', 'banana', 'cherry']
```

</details>

<details>
  <summary>71. Python Lists - Access Items</summary>

```py
thislist = ["apple", "banana", "cherry"]
print(thislist[1])

```

```py
# banana
```

```py
thislist = ["apple", "banana", "cherry"]
print(thislist[-1])

```

```py
# cherry
```

```py
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[2:5])

#This will return the items from position 2 to 5.

#Remember that the first item is position 0,
#and note that the item in position 5 is NOT included

```

```py
# ['cherry', 'orange', 'kiwi']
```

```py
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[:4])

#This will return the items from index 0 to index 4.

#Remember that index 0 is the first item, and index 4 is the fifth item
#Remember that the item in index 4 is NOT included

```

```py
# ['apple', 'banana', 'cherry', 'orange']
```

```py
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[2:])

#This will return the items from index 2 to the end.

#Remember that index 0 is the first item, and index 2 is the third
```

```py
# ['cherry', 'orange', 'kiwi', 'melon', 'mango']
```

```py
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[-4:-1])

#Negative indexing means starting from the end of the list.

#This example returns the items from index -4 (included) to index -1 (excluded)

#Remember that the last item has the index -1,

```

```py
# ['orange', 'kiwi', 'melon']
```

</details>

<details>
  <summary>72. Python Lists - Check if Item Exists </summary>

```py
thislist = ["apple", "banana", "cherry"]
if "apple" in thislist:
  print("Yes, 'apple' is in the fruits list")
```

```py
# Yes, 'apple' is in the fruits list
```

</details>

<details>
  <summary>73. Python Lists - Change Item Value</summary>

```py
thislist = ["apple", "banana", "cherry"]
thislist[1] = "blackcurrant"

print(thislist)

```

```py
# ['apple', 'blackcurrant', 'cherry']
```

```py
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]

thislist[1:3] = ["blackcurrant", "watermelon"]

print(thislist)

```

```py
# ['apple', 'blackcurrant', 'watermelon', 'orange', 'kiwi', 'mango']
```

```py
thislist = ["apple", "banana", "cherry"]

thislist[1:2] = ["blackcurrant", "watermelon"]

print(thislist)

```

```py
# ['apple', 'blackcurrant', 'watermelon', 'cherry']
```

```py
thislist = ["apple", "banana", "cherry"]

thislist[1:3] = ["watermelon"]

print(thislist)

```

```py
# ['apple', 'watermelon']
```

</details>

<details>
  <summary>74. Python Lists - Insert() method </summary>

- To insert a new list item, without replacing any of the existing values, we can use the insert() method.

- The insert() method inserts an item at the specified index.

```py
thislist = ["apple", "banana", "cherry"]

thislist.insert(2, "watermelon")

print(thislist)

```

```py
# ['apple', 'banana', 'watermelon', 'cherry']
```

```py
thislist = ["apple", "banana", "cherry"]
thislist.insert(1, "orange")
print(thislist)

```

```py
# ['apple', 'orange', 'banana', 'cherry']
```

</details>

<details>
  <summary>75. Python Lists - Append() method </summary>

To add an item to the end of the list, use the append() method.

```py
thislist = ["apple", "banana", "cherry"]

thislist.append("orange")

print(thislist)

```

```py
# ['apple', 'banana', 'cherry', 'orange']
```

</details>

<details>
  <summary>76. Python Lists - Extend() method</summary>

To append elements from another list to the current list, use the extend() method.

```py
thislist = ["apple", "banana", "cherry"]
tropical = ["mango", "pineapple", "papaya"]

thislist.extend(tropical)

print(thislist)

```

```py
# ['apple', 'banana', 'cherry', 'mango', 'pineapple', 'papaya']
```

```py
thislist = ["apple", "banana", "cherry"]
thistuple = ("kiwi", "orange")

thislist.extend(thistuple)

print(thislist)

```

```py
# ['apple', 'banana', 'cherry', 'kiwi', 'orange']
```

</details>

<details>
  <summary>77. Python Lists - remove() method </summary>

The remove() method removes the specified item.

```py
thislist = ["apple", "banana", "cherry"]
thislist.remove("banana")
print(thislist)

```

```py
# ['apple', 'cherry']
```

</details>

<details>
  <summary>78. Python Lists - pop() method </summary>

The pop() method removes the specified index.

```py
thislist = ["apple", "banana", "cherry"]
thislist.pop(1)
print(thislist)

```

```py
# ['apple', 'cherry']
```

```py
thislist = ["apple", "banana", "cherry"]
thislist.pop()
print(thislist)

```

```py
# ['apple', 'banana']
```

</details>

<details>
  <summary>79. Python Lists - del keyword </summary>

The del keyword also removes the specified index.

```py
thislist = ["apple", "banana", "cherry"]
del thislist[0]
print(thislist)

```

```py
# ['banana', 'cherry']
```

```py
thislist = ["apple", "banana", "cherry"]
del thislist
print(thislist) #this will cause an error because you have succsesfully deleted "thislist".
```

```py
# Traceback (most recent call last):
#   File "demo_list_del2.py", line 3, in <module>
#     print(thislist) #this will cause an error because you have succsesfully deleted "thislist".
# NameError: name 'thislist' is not defined
```

</details>

<details>
  <summary>80. Python Lists - clear() method </summary>

- The clear() method empties the list.

- The list still remains, but it has no content.

```py
thislist = ["apple", "banana", "cherry"]
thislist.clear()
print(thislist)
```

```py
# []
```

</details>

<details>
  <summary>81. Python Lists - Loop Through a List </summary>

You can loop through the list items by using a for loop.

```py
thislist = ["apple", "banana", "cherry"]
for x in thislist:
  print(x)

```

```py
# apple
# banana
# cherry
```

</details>

<details>
  <summary>82. Python Lists - Loop Through the Index Numbers</summary>

- You can also loop through the list items by referring to their index number.

- Use the range() and len() functions to create a suitable iterable.

```py
thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
  print(thislist[i])
```

```py
# apple
# banana
# cherry
```

</details>

<details>
  <summary>83. Python Lists - While Loop </summary>

- You can loop through the list items by using a while loop.

- Use the len() function to determine the length of the list, then start at 0 and loop your way through the list items by referring to their indexes.

- Remember to increase the index by 1 after each iteration.

```py
thislist = ["apple", "banana", "cherry"]
i = 0
while i < len(thislist):
  print(thislist[i])
  i = i + 1

```

```py
# apple
# banana
# cherry
```

</details>

<details>
  <summary>84. Python Lists - List Comprehension</summary>

The Syntax:

```bs
newlist = [expression for item in iterable if condition == True]
```

List Comprehension offers the shortest syntax for looping through lists.

```py
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]

```

```py
# apple
# banana
# cherry
```

```py
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = []

for x in fruits:
  if "a" in x:
    newlist.append(x)

print(newlist)

```

```py
# ['apple', 'banana', 'mango']
```

```py
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = [x for x in fruits if "a" in x]

print(newlist)

```

```py
# ['apple', 'banana', 'mango']
```

```py
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x for x in fruits if x != "apple"]

print(newlist)

```

```py
# ['banana', 'cherry', 'kiwi', 'mango']
```

```py
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x for x in fruits]

print(newlist)

```

```py
# ['apple', 'banana', 'cherry', 'kiwi', 'mango']
```

```py
newlist = [x for x in range(10)]

print(newlist)

```

```py
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

```py
newlist = [x for x in range(10) if x < 5]

print(newlist)

```

```py
# [0, 1, 2, 3, 4]
```

```py
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x.upper() for x in fruits]

print(newlist)

```

```py
# ['APPLE', 'BANANA', 'CHERRY', 'KIWI', 'MANGO']
```

```py
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = ['hello' for x in fruits]

print(newlist)

```

```py
# ['hello', 'hello', 'hello', 'hello', 'hello']
```

```py
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x if x != "banana" else "orange" for x in fruits]

print(newlist)

```

```py
# ['apple', 'orange', 'cherry', 'kiwi', 'mango']
```

</details>

<details>
  <summary>85. Python Lists - Sort Ascending </summary>

List objects have a sort() method that will sort the list alphanumerically, ascending, by default.

```py
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]

thislist.sort()

print(thislist)

```

```py
# ['banana', 'kiwi', 'mango', 'orange', 'pineapple']
```

```py
thislist = [100, 50, 65, 82, 23]

thislist.sort()

print(thislist)

```

```py
# [23, 50, 65, 82, 100]
```

</details>

<details>
  <summary>86. Python Lists - Sort Descending</summary>

```py
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]

thislist.sort(reverse = True)

print(thislist)

```

```py
# ['pineapple', 'orange', 'mango', 'kiwi', 'banana']
```

```py
thislist = [100, 50, 65, 82, 23]

thislist.sort(reverse = True)

print(thislist)

```

```py
# [100, 82, 65, 50, 23]
```

</details>

<details>
  <summary>87. Python Lists - Customize Sort </summary>

```py
def myfunc(n):
  return abs(n - 50)

thislist = [100, 50, 65, 82, 23]

thislist.sort(key = myfunc)

print(thislist)

```

```py
# [50, 65, 23, 82, 100]
```

</details>

<details>
  <summary>88. Python Lists - Case Insensitive </summary>

By default the sort() method is case sensitive, resulting in all capital letters being sorted before lower case letters.

```py
thislist = ["banana", "Orange", "Kiwi", "cherry"]

thislist.sort()

print(thislist)

```

```py
# ['Kiwi', 'Orange', 'banana', 'cherry']
```

```py
thislist = ["banana", "Orange", "Kiwi", "cherry"]

thislist.sort(key = str.lower)

print(thislist)

```

```py
# ['banana', 'cherry', 'Kiwi', 'Orange']
```

</details>

<details>
  <summary>89. Python Lists - Reverse Order of List </summary>

- What if you want to reverse the order of a list, regardless of the alphabet?

- The reverse() method reverses the current sorting order of the elements.

```py
thislist = ["banana", "Orange", "Kiwi", "cherry"]

thislist.reverse()

print(thislist)

```

```py
# ['cherry', 'Kiwi', 'Orange', 'banana']
```

</details>

<details>
  <summary>99. Python Lists - Copy Lists </summary>

- You cannot copy a list simply by typing list2 = list1, because: list2 will only be a reference to list1, and changes made in list1 will automatically also be made in list2.

- There are ways to make a copy, one way is to use the built-in List method copy().

- Another way to make a copy is to use the built-in method list().

```py
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()
print(mylist)

```

```py
# ['apple', 'banana', 'cherry']
```

```py
thislist = ["apple", "banana", "cherry"]
mylist = list(thislist)
print(mylist)

```

```py
# ['apple', 'banana', 'cherry']
```

</details>

<details>
  <summary>100. Python Lists - Join Lists</summary>

- There are several ways to join, or concatenate, two or more lists in Python.

- One of the easiest ways are by using the + operator.

- Another way to join two lists is by appending all the items from list2 into list1, one by one.

- Or you can use the extend() method, which purpose is to add elements from one list to another list.

```py
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3)

```

```py
# ['a', 'b', 'c', 1, 2, 3]
```

```py
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

for x in list2:
  list1.append(x)

print(list1)

```

```py
# ['a', 'b', 'c', 1, 2, 3]
```

```py
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list1.extend(list2)
print(list1)

```

```py
# ['a', 'b', 'c', 1, 2, 3]
```

</details>

<details>
  <summary>101. Python Lists - count() Method </summary>

The count() method returns the number of elements with the specified value.

```py
fruits = ["apple", "banana", "cherry"]

x = fruits.count("cherry")

print(x)

```

```py
# 1
```

```py
fruits = [1, 4, 2, 9, 7, 8, 9, 3, 1]

x = fruits.count(9)

print(x)

```

```py
# 2
```

</details>

<details>
  <summary>102. Python Lists - extend() Method </summary>

The extend() method adds the specified list elements (or any iterable) to the end of the current list.

```py
fruits = ['apple', 'banana', 'cherry']

cars = ['Ford', 'BMW', 'Volvo']

fruits.extend(cars)

print(fruits)
```

```py
# ['apple', 'banana', 'cherry', 'Ford', 'BMW', 'Volvo']
```

```py
fruits = ['apple', 'banana', 'cherry']

points = (1, 4, 5, 9)

fruits.extend(points)

print(fruits)

```

```py
# ['apple', 'banana', 'cherry', 1, 4, 5, 9]
```

</details>

<details>
  <summary>103. Python Lists - index() Method </summary>

The index() method returns the position at the first occurrence of the specified value.

```py
fruits = ['apple', 'banana', 'cherry']

x = fruits.index("cherry")

print(x)

```

```py
# 2
```

```py
fruits = [4, 55, 64, 32, 16, 32]

x = fruits.index(32)

print(x)

```

```py
# 3
```

</details>

<details>
  <summary>104. Python Lists - reverse() Method </summary>

The reverse() method reverses the sorting order of the elements.

```py
fruits = ['apple', 'banana', 'cherry']

fruits.reverse()

print(fruits)

```

```py
# ['cherry', 'banana', 'apple']
```

</details>

<details>
  <summary>105. Python Lists - sort() Method </summary>

- The sort() method sorts the list ascending by default.

- You can also make a function to decide the sorting criteria(s).

```py
cars = ['Ford', 'BMW', 'Volvo']

cars.sort()

print(cars)

```

```py
# ['BMW', 'Ford', 'Volvo']
```

```py
cars = ['Ford', 'BMW', 'Volvo']

cars.sort(reverse=True)

print(cars)

```

```py
# ['Volvo', 'Ford', 'BMW']
```

```py
# A function that returns the length of the value:
def myFunc(e):
  return len(e)

cars = ['Ford', 'Mitsubishi', 'BMW', 'VW']

cars.sort(key=myFunc)

print(cars)

```

```py
# ['VW', 'BMW', 'Ford', 'Mitsubishi']
```

```py
def myFunc(e):
  return e['year']

cars = [
  {'car': 'Ford', 'year': 2005},
  {'car': 'Mitsubishi', 'year': 2000},
  {'car': 'BMW', 'year': 2019},
  {'car': 'VW', 'year': 2011}
]

cars.sort(key=myFunc)

print(cars)

```

```py
# [{'car': 'Mitsubishi', 'year': 2000}, {'car': 'Ford', 'year': 2005}, {'car': 'VW', 'year': 2011}, {'car': 'BMW', 'year': 2019}]
```

```py
# A function that returns the length of the value:
def myFunc(e):
  return len(e)

cars = ['Ford', 'Mitsubishi', 'BMW', 'VW']

cars.sort(reverse=True, key=myFunc)

print(cars)

```

```py
# ['Mitsubishi', 'Ford'', 'BMW', 'VW']
```

</details>

<details>
  <summary>106.  </summary>

# Example 1 -

```py

```

```py

```

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>107.  </summary>

# Example 1 -

```py

```

```py

```

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>108.  </summary>

# Example 1 -

```py

```

```py

```

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>109.  </summary>

# Example 1 -

```py

```

```py

```

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>110.  </summary>

# Example 1 -

```py

```

```py

```

```py

```

```py

```

```py

```

```py

```

</details>
