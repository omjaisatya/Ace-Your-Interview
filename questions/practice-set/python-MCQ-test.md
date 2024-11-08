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
