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
```python
try:
    # risky code
except ValueError:
    print("Invalid value")
except ZeroDivisionError:
    print("Division by zero")
except:
    print("Some other exception occurred")
```
## What is the purpose of the final except branch?
It's just a backup to catch any other errors that ValueError or ZeroDivisionError miss.
## When would it execute?
It runs if an error happens that isn't a ValueError or ZeroDivisionError (like a TypeError or IndexError).
## Why must the default except branch appear last?
Python checks except blocks from top to bottom. If the default one was first, it would grab every error right away and Python would never reach the specific ones underneath.
## Why are specific exception handlers usually more informative than relying only on a default handler?
Specific handlers tell you what actually broke so you can show a helpful error message. A default handler hides the real problem, which makes it annoying to debug.
# Part 8 — Syntax Errors Are Different
```python
if value > 0
    print("Positive")
```
## What kind of error is present?
SyntaxError
## Locate the defect.
Missing a colon : at the end of if value > 0.
## Why should the programmer correct this problem rather than attempt to hide it with ordinary exception-handling logic?
Because Python can't even run or load the code if there's a syntax error, so a try-except block won't catch it. You just have to fix the code directly.

# Part 9 — Test Every Execution Path
```python
number = float(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```
| Test Input | Expected Path | Expected Result | Actual Result | Pass/Fail |
| --- | --- | --- | --- | --- |
| 5 | if number > 0: | Positive | Positive | Pass |
| -3 | elif number < 0: | Negative | Negative | Pass |
| 0 | else: | Zero | Zero | Pass |
## Explain why one successful test does not demonstrate that every path works correctly.
Testing just one input only checks that single branch. The other branches could still have typos or bad logic that you won't see unless you test inputs for them too.

# Part 10 — Find the Hidden Bug
```python
value = float(input("Enter a number: "))

if value > 0:
    print("Positive")
elif value < 0:
    prin("Negative")
else:
    print("Zero")
```
## Does the program appear to work for that test (0)?
Yeah, entering 0 goes straight to the else: path, so it prints Zero without throwing an error.
## Which execution path contains the bug?
The elif value < 0: path.
## What test input will expose it?
Any negative number, like -5.
## What does this demonstrate about testing different execution paths?
It shows code can look totally fine on one test input, but still have game-breaking bugs sitting in paths you didn't run.
```python
value = float(input("Enter a number: "))

if value > 0:
    print("Positive")
elif value < 0:
    print("Negative")
else:
    print("Zero")
```
# Part 11 — Print Debugging
## Before changing the code, calculate the expected result manually:
## 50.0
## Run the program and record the actual result:
## 16.5
## Code with temporary print() statements:
## The following program is intended to calculate the total cost of several identical items, but it contains a logical error.
```python
def calculate_total(price, quantity):
    print("DEBUG: price =", price, "quantity =", quantity)
    total = price + quantity
    print("DEBUG: total =", total)
    return total

price = float(input("Price: "))
quantity = int(input("Quantity: "))

result = calculate_total(price, quantity)
print("Total:", result)
```
## For each debugging statement, explain what information it provides:
The first print shows that 12.5 and 4 got passed into the function correctly.
The second print shows that total came out to 16.5, showing that the program added the numbers instead of multiplying them.
Identify and correct the logical error:
The error was using + instead of * in total = price + quantity. It should be total = price * quantity.
```python
def calculate_total(price, quantity):
    total = price * quantity
    return total

price = float(input("Price: "))
quantity = int(input("Quantity: "))

result = calculate_total(price, quantity)
print("Total:", re
```
# Part 12 — Integrated Exception-Handling Program
## Create a Python program that asks the user for two integers and divides the first number by the second.
```python
try:
    num1 = int(input("Enter first integer: "))
    num2 = int(input("Enter second integer: "))
    result = num1 / num2
    print("Result:", result)
except ValueError:
    print("Error: You have to enter valid whole numbers.")
except ZeroDivisionError:
    print("Error: You can't divide by zero.")

print("Done running.")
```
Input 1 | Input 2 | Expected Path | Expected Result | Actual Result | Pass/Fail |
| --- | --- | --- | --- | --- | --- |
| 10 | 2 | try block | Result: 5.0 | Result: 5.0 | Pass |
| 10 | 0 | except ZeroDivisionError: | Error message | Error message | Pass |
| abc | 5 | except ValueError: | Error message | Error message | Pass |
| 10 | xyz | except ValueError: | Error message | Error message | Pass |

# Analysis and Reflection
## 1. What does it mean for an exception to be raised?
It means Python hit something wrong while running the code, so it stopped normal execution to throw an error flag.
## 2. What happens to the remaining statements in a try block after an exception occurs?
Python completely skips the rest of the code in the try block and jumps straight down to the matching except block.
## 3. Why can separate exception handlers be more useful than one generic handler?
Because specific handlers tell the user exactly what went wrong (like dividing by zero vs typing letters instead of numbers) instead of giving a useless generic error.
## 4.Why does handling an exception not prove that a program is bug-free?
Because catching exceptions just keeps the program from crashing on bad input. It won't catch bad math, wrong logic, or typos in paths that run without throwing errors.
## 5. Why should every important execution path be tested?
Because a path you didn't test could easily have a hidden typo or logic bug that only triggers when a specific input runs through it.
## 6. How can print debugging help locate a logical error?
It lets you track what your variables are doing at each step so you can spot the exact line where the math or logic goes off track.
