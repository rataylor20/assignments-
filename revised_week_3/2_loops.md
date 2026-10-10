# CISC 179 - Week 3
## Loops

This assignment covers Python Loops

## code and answers 

# 1. While loop
## a. Please write Python code using a while loop to perform the following steps.
    1    Take any non-negative and non-zero integer number and name it n0
    2    if the number is even, evaluate a new n0 as n0 ÷ 2;
    3    Otherwise, if the number is odd, evaluate a new n0 as 3 * n0 + 1;
    4    if n0 is not equal to 1, go to point 2.
Sample input: 16
Expected output:
8
4
2
1
steps = 4
```python
n0 = int(input("Enter a non negative, non zero integer: "))
steps = 0

while n0 != 1:
    if n0 % 2 == 0:
        n0 = n0 // 2
    else:
        n0 = 3 * n0 + 1
    print(n0)
    steps += 1

print(f"steps = {steps}")
```
## prompt:
Enter a non negative, non zero integer: 16

8

4

2

1

steps = 4

Process finished with exit code 0

## b. Write code that uses a while loop and runs indefinitely. Modify the same code to resolve the infinite loop issue.
```python
count = 5
while count > 0:
    print(count)
```
corrected
```python
count = 5
while count > 0:
    print(count)
    count -= 1
```

## c. Write a program that takes two integers as input and asks the user to choose an arithmetic operation to perform with those numbers. At the end of the program, prompt the user with the question, "Do you want to continue?" If the user selects "Y" or "y," the program should restart; otherwise, it should exit and display the message, "Have a good day."
``` while True:
    num1 = int(input("Enter first integer: "))
    num2 = int(input("Enter second integer: "))
    op = input("Choose an arithmetic operation (+, -, *, /): ")

    if op == '+':
        print(f"Result: {num1 + num2}")
    elif op == '-':
        print(f"Result: {num1 - num2}")
    elif op == '*':
        print(f"Result: {num1 * num2}")
    elif op == '/':
        if num2 != 0:
            print(f"Result: {num1 / num2}")
        else:
            print("Error: Division by zero is not allowed.")
    else:
        print("Invalid operation.")

    choice = input("Do you want to continue? (Y/y): ")
    if choice != 'Y' and choice != 'y':
        print("Have a good day.")
        break
```
# 2. For loops

## a. Write a code that counts the total number of characters in a text and also counts each character individually. For example, consider the sentence "To be, or not to be, that is the question." The code should determine the total number of letters and how many times each letter appears, including specific counts for the letters 't' and 'o', etc. Ignore the upper and lower cases letters, and any punctuations symbols. Use only for loop, while loop, break and continue statements where necessary.
Sample input: To be, or not to be, that is the question
Expected output:
Total number of alphabets: 30
Total number of distinct alphabets are:
T = 7
o = 4
Note: The expected output above is incomplete. The sum of the total distinct alphabets must equal the total number of alphabets in the given text.
```python
text = "To be, or not to be, that is the question"
cleaned_text = ""
for char in text:
    if char.isalpha():
        cleaned_text += char.lower()
total_alphabets = len(cleaned_text)
counts = {}
for char in cleaned_text:
    if char in counts:
        counts[char] += 1
    else:
        counts[char] = 1
print(f"Total number of alphabets: {total_alphabets}")
print("Total number of distinct alphabets are:")
for char, count in counts.items():
    print(f"{char} = {count}")
```
