# CISC 179 - Week 5
## Exceptions and Debugging 

This assignment covers Python exceptions and debugging 

# code and answers 


# Part 1 — Errors in Data vs. Errors in Cod
## 1.The program expects an integer but the user enters hello.  
Bad input, used words instead of numbers .
## 2. the programmer writes prin() instead of print().

## 3. The program divides by a value entered by the user, and the user enters 0 .
Bad input, you cant divide by 0.

# Part 2 — Reading an Exc

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
