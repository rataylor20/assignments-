# CISC 171 - Week 2
## Python literals
from platform import python_branch

## This Assignments covers Python literals

## code and answers

```python
# 1 Literals
print(5 * 2 - 2)
# 8

print(5 /2)
# 2.5

print(6 // 2)
# 3

print(2 ** 3)
# 8

print(2 ** 4)
# 16

print(2 ** -2)
# 0.25

print("hello " + "World")

print("bla " * 3)
# bla bla bla

print(2 ** 3 ** 1)
# 8

print(5 * 25 // 13 + 100 / 2 % 11 // 2)
# 12.0

print(2 ** 3 ** 5)
# 14134776518227074636666380005943348126619871175004951664972849610340958208

print((2 ** 4), (2 ** 4), (2 ** -2))
# 16 16 0.25

# 2 Data type

type("hello")
# <class 'str'>

type(1 + 2)
# <class 'int'>

type(1.1)
# <class 'float'>

type("A")
# <class 'str'>

type(500)
# <class 'int'>

type(True)
# <class 'bool'>

type(False)
# <class 'str'

# 3. Operator precedure
#A
print(5 + (2 ** -3) * 4)
#B
# 5.5

# Challenges
#1 Figuring out why PyCharm threw a warning ("Statement seems to have no effect") until I remembered to wrap the expression in a print() function
#2 Accounting for how negative exponents automatically convert results into floats, which changed my expected output.
#3 Keeping track of the right-to-left evaluation rule for exponents (**) compared to standard left-to-right math operations.
