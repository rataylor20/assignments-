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
if enter is pressed nothing is submitted and int() cant read a empty submission
## 3. What information does the exception name provide to the programmer?
python received the wrong type of value
## 4. If the user entered 0 instead, would the same exception occur? Explain.
no like in part one this is a bad input not a bug in the code itself the code works it gives error on next line due to not being able to divide by 0
# Part 3 — Complete a Basic try-except
```python
try:
    value = int(input("enter an integer: "))
    print("You entered:", value)
except ValueError:
    print("Please enter an integer")
```
 ## input 4
 PRE. "you entered; 4"
 RES. "You entered 4"
 ## input "abc"
 PRE. error "Thats not a valid integer!
 RES. "That's not a valid integer! 
 ## input ()
 PRE. error "Thats not a valid integer!
 RES. "That's not a valid integer! 

# Part 4 — Trace try-except Control Flow
```python
try:
    print("A")
    value = int(input("Enter a number: "))
    print("B")
    result = 10 / value
    print("C")
except ValueError:
    print("Invalid value")
except ZeroDivisionError:
    print("Cannot divide by zero")

print("D")
```
## Input 2:
Lines Executed: print("A"), int(), print("B"), 10 / value, print("C"), print("D")
Lines Skipped: Both except blocks
#Exception: None
## Input "0":
Lines Executed: print("A"), int(), print("B"), 10 / value (fails), except ZeroDivisionError, print("D")
Lines Skipped: print("C"), except ValueError
Exception: ZeroDivisionError
## Input "hello":
Lines Executed: print("A"), int() (fails), except ValueError, print("D")
Lines Skipped: print("B"), 10 / value, print("C"), except ZeroDivisionError
Exception: ValueError
 ## input 2
A
Enter a number: 2
B
C
D

Process finished with exit code 0
 ## input "0"
A
Enter a number: 0
B
Cannot divide by zero
D

Process finished with exit code 0 
 ## input (hello)
 A
Enter a number: hello
Invalid value
D

Process finished with exit code 0
## Why doesn't print("C") run when dividing by zero?
Because 10 / value crashes with an error before Python can even get to print("C"). As soon as Python hits an error inside a try block, it skips everything else in that block and jumps straight to the except part.

# Part 5 — Handle More Than One Exception
```python
try:
    num = int(input("Enter an integer: "))
    reciprocal = 1 / num
    print("The reciprocal is:", reciprocal)
except ValueError:
    print("That's not a valid whole number!")
except ZeroDivisionError:
```

## outcomes
(5): Prints The reciprocal is: 0.2
(0): Catches the zero error and prints You can't calculate the reciprocal of zero!
(abc): Catches the value error and prints That's not a valid whole number!
(): Catches the value error and prints That's not a valid whole number!


# Part 6 — Common Python Exceptions
 ## For each fragment, identify the exception and explain the operation that causes it.

## A
number = int("hello")

Exc: ValueError

Exp: int() can't turn "hello" into a number because it's words, not digits.
## B
result = 10 % 0

Exc: ZeroDivisionError

Exp: You can't divide 10 by zero in math, so Python crashes.

## C
values = [10, 20, 30]


print(values[1.5])

Exc: NameError

Exp: Python has no idea what x is because it was never set up as a variable.
## D
values = [1, 2]

values.depend(3)

Use the exception names ValueError, ZeroDivisionError, TypeError, and AttributeErrorwhere appropriate.

Exc: TypeError

Exp: Python won't let you mix and add string text ("2") directly with a regular number (2).

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
