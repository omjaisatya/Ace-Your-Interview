# Python Interview MCQs -- Set A

### 1. What is the output of the following code?

```python
print(type([]) is list)
```

- A) True
- B) False
- C) None
- D) Error

**Answer**: A) True  
**Explanation**: `type([])` returns `<class 'list'>`, and `is` checks for identity, which in this case is `True`.

---

### 2. Which of the following is used to define a block of code in Python?

- A) Curly braces `{ }`
- B) Parentheses `( )`
- C) Indentation
- D) Square brackets `[ ]`

**Answer**: C) Indentation  
**Explanation**: Python uses indentation (whitespace) to define code blocks, rather than curly braces or any other symbol.

---

### 3. What is the output of the following code?

```python
x = "Python"
print("t" in x)
```

- A) True
- B) False
- C) Error
- D) None

**Answer**: A) True  
**Explanation**: The expression `"t" in x` checks if the character `"t"` exists in the string `x`, which is `"Python"`. It returns `True` as `"t"` is indeed in `"Python"`.

---

### 4. What is the correct syntax to output "Hello World" in Python?

- A) `echo("Hello World")`
- B) `print("Hello World")`
- C) `printf("Hello World")`
- D) `println("Hello World")`

**Answer**: B) `print("Hello World")`  
**Explanation**: `print()` is the correct function to output text in Python.

---

### 5. Which of the following data types is immutable in Python?

- A) List
- B) Dictionary
- C) Set
- D) Tuple

**Answer**: D) Tuple  
**Explanation**: Tuples are immutable, meaning their values cannot be changed after they are created.

---

### 6. What will be the output of the following code?

```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)
```

- A) `[1, 2, 3]`
- B) `[1, 2, 3, 4]`
- C) `[4, 1, 2, 3]`
- D) Error

**Answer**: B) `[1, 2, 3, 4]`  
**Explanation**: `b` is a reference to `a`, so changes made to `b` also affect `a`.

---

### 7. What is the output of the following code?

```python
print("hello" * 3)
```

- A) `hellohellohello`
- B) `hello3`
- C) `Error`
- D) `hello hello hello`

**Answer**: A) `hellohellohello`  
**Explanation**: The `*` operator repeats the string `"hello"` three times.

---

### 8. Which keyword is used for function in Python?

- A) func
- B) define
- C) function
- D) def

**Answer**: D) def  
**Explanation**: In Python, `def` is the keyword used to define functions.

---

### 9. Which of these is not a core data type in Python?

- A) List
- B) Dictionary
- C) Tuples
- D) Class

**Answer**: D) Class  
**Explanation**: Class is a user-defined blueprint for objects, not a core data type.

---

### 10. What will be the output of the following code?

```python
print(bool("False"))
```

- A) True
- B) False
- C) Error
- D) None

**Answer**: A) True  
**Explanation**: Any non-empty string is considered `True` in Python, regardless of its content.

# Python Interview MCQs -- Set B

### 1. What is the output of the following code?

```python
print(3 * 1**3)
```

- A) 3
- B) 1
- C) 9
- D) 27

**Answer**: A) 3  
**Explanation**: The expression `1**3` evaluates to `1`, and `3 * 1` is `3`.

---

### 2. What does the following code output?

```python
print(bool(0), bool(3.14159))
```

- A) False True
- B) True True
- C) False False
- D) True False

**Answer**: A) False True  
**Explanation**: `bool(0)` is `False` since `0` is considered `False` in Python, while any non-zero number (like `3.14159`) is `True`.

---

### 3. What is the output of the following code?

```python
x = [1, 2, 3]
print(x.pop(1))
print(x)
```

- A) 1, [2, 3]
- B) 2, [1, 3]
- C) 3, [1, 2]
- D) Error

**Answer**: B) 2, [1, 3]  
**Explanation**: `x.pop(1)` removes and returns the element at index `1`, which is `2`. The list `x` then becomes `[1, 3]`.

---

### 4. Which of the following functions can be used to get the length of a list in Python?

- A) `length()`
- B) `size()`
- C) `len()`
- D) `count()`

**Answer**: C) `len()`  
**Explanation**: `len()` is used to get the length of a list (or any sequence) in Python.

---

### 5. What will be the output of the following code?

```python
print("Hello {0} and {1}".format("Alice", "Bob"))
```

- A) `Hello {0} and {1}`
- B) `Hello Alice and Bob`
- C) `Hello {Alice} and {Bob}`
- D) Error

**Answer**: B) `Hello Alice and Bob`  
**Explanation**: `str.format()` replaces placeholders `{0}` and `{1}` with "Alice" and "Bob".

---

### 6. Which operator is used to check if two values are not equal in Python?

- A) `<>`
- B) `=`
- C) `==`
- D) `!=`

**Answer**: D) `!=`  
**Explanation**: `!=` is used to check if two values are not equal in Python.

---

### 7. What will be the output of the following code?

```python
x = 10
y = 5
x, y = y, x
print(x, y)
```

- A) 10 5
- B) 5 10
- C) Error
- D) None

**Answer**: B) 5 10  
**Explanation**: `x, y = y, x` swaps the values of `x` and `y`.

---

### 8. What is the output of the following code?

```python
def add(a, b=2):
    return a + b

print(add(3))
```

- A) 3
- B) 5
- C) Error
- D) None

**Answer**: B) 5  
**Explanation**: The function `add` has a default parameter `b=2`, so `add(3)` is equivalent to `add(3, 2)`, which returns `5`.

---

### 9. Which of the following statements is correct about Python lists?

- A) Lists are immutable.
- B) Lists can contain elements of different types.
- C) Lists cannot contain duplicate elements.
- D) Lists are unordered.

**Answer**: B) Lists can contain elements of different types.  
**Explanation**: Python lists are mutable, can contain duplicates, and are ordered. They can store elements of any type.

---

### 10. What does the following code print?

```python
print({1, 2, 3} & {2, 3, 4})
```

- A) `{1, 2, 3, 4}`
- B) `{2, 3}`
- C) `{1}`
- D) `None`

**Answer**: B) `{2, 3}`  
**Explanation**: The `&` operator returns the intersection of two sets, which is `{2, 3}` in this case.

# Python Interview MCQs -- Set C

### 1. What will be the output of the following code?

```python
print("python".capitalize())
```

- A) Python
- B) PYTHON
- C) python
- D) error

**Answer**: A) Python  
**Explanation**: The `capitalize()` method capitalizes the first character of the string and makes all other characters lowercase.

---

### 2. What is the data type of `None` in Python?

- A) `bool`
- B) `str`
- C) `NoneType`
- D) `int`

**Answer**: C) `NoneType`  
**Explanation**: `None` is a special constant in Python representing the absence of a value or a null value, and its type is `NoneType`.

---

### 3. What will be the output of the following code?

```python
a = [1, 2, 3]
print(a * 2)
```

- A) `[1, 2, 3, 1, 2, 3]`
- B) `[2, 4, 6]`
- C) `6`
- D) Error

**Answer**: A) `[1, 2, 3, 1, 2, 3]`  
**Explanation**: Multiplying a list by an integer (like `2`) duplicates the list elements by that integer.

---

### 4. Which of the following keywords is used to create an exception in Python?

- A) `try`
- B) `catch`
- C) `throw`
- D) `raise`

**Answer**: D) `raise`  
**Explanation**: The `raise` keyword is used to manually raise exceptions in Python.

---

### 5. What is the output of the following code?

```python
a = [1, 2, 3, 4, 5]
print(a[2:4])
```

- A) `[2, 3, 4]`
- B) `[3, 4]`
- C) `[1, 2, 3, 4]`
- D) `[3, 4, 5]`

**Answer**: B) `[3, 4]`  
**Explanation**: The slice `[2:4]` starts at index `2` and stops just before index `4`, so it includes elements at index `2` and `3` only.

---

### 6. What is the output of the following code?

```python
x = {1, 2, 3}
y = {2, 3, 4}
print(x | y)
```

- A) `{1, 2, 3, 4}`
- B) `{2, 3}`
- C) `{1, 4}`
- D) Error

**Answer**: A) `{1, 2, 3, 4}`  
**Explanation**: The `|` operator returns the union of two sets, which includes all unique elements from both sets.

---

### 7. Which of the following statements is false about Python dictionaries?

- A) Dictionaries are unordered collections.
- B) Dictionary keys must be unique.
- C) Dictionary values must be unique.
- D) Dictionaries use key-value pairs.

**Answer**: C) Dictionary values must be unique.  
**Explanation**: Dictionary keys must be unique, but values can be duplicated.

---

### 8. What is the output of the following code?

```python
print(10 // 3)
```

- A) `3.33`
- B) `3`
- C) `4`
- D) `10.0`

**Answer**: B) `3`  
**Explanation**: `//` is the floor division operator, which performs integer division and discards the decimal part.

---

### 9. Which of the following is not a valid Python variable name?

- A) `_my_var`
- B) `2var`
- C) `my_var`
- D) `myVar2`

**Answer**: B) `2var`  
**Explanation**: Variable names in Python cannot start with a number.

---

### 10. What will be the output of the following code?

```python
def func(a, b=5, c=10):
    print(a, b, c)

func(3, c=20)
```

- A) `3 5 10`
- B) `3 5 20`
- C) `3 20 10`
- D) Error

**Answer**: B) `3 5 20`  
**Explanation**: The function `func` is called with `a=3` and `c=20`, while `b` uses its default value of `5`.

---

### 11. What will be the output of the following code?

```python
print("abcde"[-1])
```

- A) `a`
- B) `e`
- C) `d`
- D) Error

**Answer**: B) `e`  
**Explanation**: Negative indexing starts from the end of the string, so `[-1]` gives the last character, which is `e`.

---

### 12. What will be the output of the following code?

```python
a = (1, 2, 3)
a[0] = 4
```

- A) `(4, 2, 3)`
- B) `(1, 2, 3)`
- C) Error
- D) `(4, 4, 3)`

**Answer**: C) Error  
**Explanation**: Tuples are immutable in Python, so attempting to change `a[0]` will raise a `TypeError`.

---

### 13. Which of the following functions can convert an integer `x` to a string in Python?

- A) `str(x)`
- B) `to_string(x)`
- C) `int(x)`
- D) `string(x)`

**Answer**: A) `str(x)`  
**Explanation**: The `str()` function converts a value to a string in Python.

---

### 14. What will be the output of the following code?

```python
x = [i**2 for i in range(3)]
print(x)
```

- A) `[1, 4, 9]`
- B) `[0, 1, 4]`
- C) `[0, 1, 2]`
- D) Error

**Answer**: B) `[0, 1, 4]`  
**Explanation**: The list comprehension `[i**2 for i in range(3)]` squares each number from `0` to `2`, producing `[0, 1, 4]`.

---

### 15. Which of the following is the correct way to open a file in write mode in Python?

- A) `open("file.txt", "r")`
- B) `open("file.txt", "w")`
- C) `open("file.txt", "rw")`
- D) `open("file.txt")`

**Answer**: B) `open("file.txt", "w")`  
**Explanation**: The `"w"` mode opens a file for writing, creating the file if it doesn’t exist or truncating it if it does.

# Python Interview MCQs - Set D

### 1. What will be the output of the following code?

```python
print(list("hello"))
```

- A) `['hello']`
- B) `['h', 'e', 'l', 'l', 'o']`
- C) `['h e l l o']`
- D) Error

**Answer**: B) `['h', 'e', 'l', 'l', 'o']`  
**Explanation**: `list("hello")` converts the string `"hello"` into a list of individual characters.

---

### 2. Which of the following keywords is used to check if a key exists in a dictionary?

- A) `includes`
- B) `exists`
- C) `in`
- D) `find`

**Answer**: C) `in`  
**Explanation**: The `in` keyword checks if a key exists in a dictionary. For example, `key in dictionary`.

---

### 3. What will be the output of the following code?

```python
x = [10, 20, 30]
y = x
y[0] = 100
print(x)
```

- A) `[100, 20, 30]`
- B) `[10, 20, 30]`
- C) `[10, 100, 30]`
- D) Error

**Answer**: A) `[100, 20, 30]`  
**Explanation**: `y` is a reference to the list `x`, so changes in `y` also affect `x`.

---

### 4. What does the `eval()` function do in Python?

- A) Converts a string to an integer
- B) Evaluates a string as a Python expression
- C) Executes a Python script
- D) Compiles Python code

**Answer**: B) Evaluates a string as a Python expression  
**Explanation**: `eval()` takes a string and evaluates it as a Python expression.

---

### 5. What is the output of the following code?

```python
print("Python"[::-1])
```

- A) `nohtyP`
- B) `Python`
- C) `nohty`
- D) `Error`

**Answer**: A) `nohtyP`  
**Explanation**: The slicing `[::-1]` reverses the string `"Python"`.

---

### 6. Which method can be used to remove whitespace from the beginning and end of a string?

- A) `strip()`
- B) `trim()`
- C) `cut()`
- D) `remove()`

**Answer**: A) `strip()`  
**Explanation**: `strip()` removes whitespace from the start and end of a string in Python.

---

### 7. What is the output of the following code?

```python
x = [1, 2, 3]
print(x.append(4))
```

- A) `[1, 2, 3, 4]`
- B) `None`
- C) `Error`
- D) `4`

**Answer**: B) `None`  
**Explanation**: The `append()` method modifies the list in place and returns `None`.

---

### 8. Which of the following statements about sets in Python is incorrect?

- A) Sets are unordered collections.
- B) Sets can contain duplicate elements.
- C) Sets support mathematical operations like union and intersection.
- D) Sets are mutable.

**Answer**: B) Sets can contain duplicate elements.  
**Explanation**: Sets are collections of unique elements, so duplicates are not allowed.

---

### 9. What will be the output of the following code?

```python
a = [1, 2, 3]
b = a[:]
b.append(4)
print(a)
```

- A) `[1, 2, 3]`
- B) `[1, 2, 3, 4]`
- C) `[4, 1, 2, 3]`
- D) Error

**Answer**: A) `[1, 2, 3]`  
**Explanation**: `b = a[:]` creates a shallow copy of `a`, so changes to `b` do not affect `a`.

---

### 10. Which of the following is used to handle exceptions in Python?

- A) `try` and `catch`
- B) `try` and `except`
- C) `catch` and `finally`
- D) `throw` and `finally`

**Answer**: B) `try` and `except`  
**Explanation**: In Python, `try` and `except` are used to handle exceptions.

---

### 11. What will be the output of the following code?

```python
print(type({}))
```

- A) `<class 'list'>`
- B) `<class 'set'>`
- C) `<class 'dict'>`
- D) `<class 'tuple'>`

**Answer**: C) `<class 'dict'>`  
**Explanation**: `{}` represents an empty dictionary in Python. An empty set is created with `set()`.

---

### 12. Which of the following expressions will raise a `ZeroDivisionError` in Python?

- A) `10 / 0`
- B) `10 * 0`
- C) `0 / 10`
- D) `0 * 10`

**Answer**: A) `10 / 0`  
**Explanation**: Dividing a number by zero raises a `ZeroDivisionError`.

---

### 13. What is the purpose of the `break` statement in Python?

- A) To exit a loop
- B) To end a function
- C) To stop the program
- D) To pause a loop temporarily

**Answer**: A) To exit a loop  
**Explanation**: The `break` statement is used to exit a loop prematurely.

---

### 14. What will be the output of the following code?

```python
for i in range(3):
    print(i)
else:
    print("Done")
```

- A) `0 1 2`
- B) `0 1 2 Done`
- C) `Done 0 1 2`
- D) `Error`

**Answer**: B) `0 1 2 Done`  
**Explanation**: The `else` block in a `for` loop executes after the loop completes normally (without a `break`).

---

### 15. Which of the following statements is used to define a lambda function in Python?

- A) `def`
- B) `lambda`
- C) `func`
- D) `define`

**Answer**: B) `lambda`  
**Explanation**: `lambda` is used to create anonymous functions (inline functions) in Python.
