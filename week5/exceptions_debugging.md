# CISC 179 - Week 5
## Exceptions and Debugging 

This assignment covers Python exceptions and debugging 

# code and answers 


# Part 1 — Errors in Data vs. Errors in Cod
## 1.The program expects an integer but the user enters hello.  
Bad input, used words instead of numbers .
## 2. the programmer writes prin() instead of print().
Bug in code, python doesnt understand "prin()"
## 3. The program divides by a value entered by the user, and the user enters 0 .
Bad input, you cant divide by 0.

# Part 2 — Reading an Exc
## The user presses Enter without typing a value and Python reports a ValueError.
```python
value = int(input("enter a natural number"))
print(1 / value)  
```
enter a natural number
Traceback (most recent call last):
  File "C:\Users\ryant\PycharmProjects\WelcomeScreen\pop.py", line 1, in <module>
    value = int(input("enter a natural number"))
ValueError: invalid literal for int() with base 10: ''

Process finished with exit code 1
## 1. Which operation causes the exception?
int()
## 2. Why does the exception occur?
ih enter is pressed nothing is submitted and int() cant read a empty submission
## 3. What information does the exception name provide to the programmer?
python received the wrong type of value
## 4. If the user entered 0 instead, would the same exception occur? Explain.
no like in part one this is a bad input not a bug in the code itself the code works it gives error on next line due to not being able to devide by 0
# Part 3 — Complete a Basic try-except

# Part 4 — Trace try-except Control Flow

# Part 5 — Handle More Than One Exception

# Part 6 — Common Python Exceptions
## For each fragment, identify the exception and explain the operation that causes it.

## A
number = int("hello")

## B
result = 10 % 0

## C
values = [10, 20, 30]
print(values[1.5])

## D
values = [1, 2]
values.depend(3)
Use the exception names ValueError, ZeroDivisionError, TypeError, and AttributeErrorwhere appropriate.
# Part 7 — The Default except Branch 
# Part 8 — Syntax Errors Are Different
# Part 9 — Test Every Execution Path
## number = float(input("Enter a number: "))
# Part 10 — Find the Hidden Bug
## value = float(input("Enter a number: "))
# Part 11 — Print Debugging
## The following program is intended to calculate the total cost of several identical items, but it contains a logical error.
# Part 12 — Integrated Exception-Handling Program
## Create a Python program that asks the user for two integers and divides the first number by the second.
