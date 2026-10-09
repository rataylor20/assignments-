# CISC 179 - Week 3
## Applying decisions statements

This assignment covers Python decisions statements

## code and answers 

Decision statements
To execute or not to execute—that is the question. I have adapted a Shakespeare quote, originally written as "To be, or not to be—that is the question." Decision statements generally work in a similar way. You evaluate an expression, and if the result is true, you perform a specific action; otherwise, you take a different action.
# 1. Comparison operators
Decision statements utilize comparison operators, and based on the True or False result, specific statements are executed.
print(2 < 5)  # this gives True
print(10 <= 10)  # this gives True
x = 10
print(20 < x)  # this gives False
print("A" < "a")  # this gives True because the ASCII of "A" is 65 and "a" is 97. The Python interpreter converts the
/# character in ASCII number and then compare.
print("Monday" > "Tuesday")  # this gives False because the first character of "Monday" (M) has a lower ASCII value
/# as compared to the first character of "Tuesday" (T)
Research and find the ASCII number of all the characters available on the keyboard using Python.
```python
keyboard = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*()_+-=[]{}|;':\",./<>? "
for char in keyboard:
    print(char, ord(char))
```
## prompt
a 97
b 98
c 99
d 100
e 101
f 102
g 103
h 104
i 105
j 106
k 107
l 108
m 109
n 110
o 111
p 112
q 113
r 114
s 115
t 116
u 117
v 118
w 119
x 120
y 121
z 122
A 65
B 66
C 67
D 68
E 69
F 70
G 71
H 72
I 73
J 74
K 75
L 76
M 77
N 78
O 79
P 80
Q 81
R 82
S 83
T 84
U 85
V 86
W 87
X 88
Y 89
Z 90
0 48
1 49
2 50
3 51
4 52
5 53
6 54
7 55
8 56
9 57
! 33
@ 64
/# 35
$ 36
% 37
^ 94
& 38
/* 42
( 40
) 41
_ 95
/+ 43
/- 45
= 61
[ 91
] 93
{ 123
} 125
| 124
; 59
' 39
: 58
" 34
, 44
. 46
/ 47
< 60
/> 62
/? 63
  32

Process finished with exit code 0


# 2. Logical operators (and, or, not)
Do not write logical operators in all uppercase like AND, OR, NOT - Syntax Error
and logical operator: Both expression's result need to be True to get the True output. If one expression's result is False, the output will be False regardless of the second expression's result. For example,
10 > 4 and 50 < 100  # True and True is True
10 < 4 and 50 < 100  # Here first expression is False, the output will be False
or logical operator: Both expression's result need to be False to get the False output. If one expression's result is True, the output will be True regardless of the second expression's result. For example,
10 < 4 or 50 > 100  # False and False is False
10 > 4 and 50 > 100  # Here first expression is True, the output will be True
not logical operator: Inverts the result
10 > 4 # this is True
not(10 > 4) # this is False
# 3. Bitwise logical operators (and, or, not, xor)
Remember bitwise logical operators operates on bits
To differentiate between logical operators and bitwise logical operators, Python uses distinct symbols for each.
Name of the logical operator
Logical operator in Python
Bitwise logical operator in Python
and
and
&
or
or
|
not
not
~
xor
-
^
Example bitwise or
x = 0b1110 # 0b represents binary number, decimal 14
y = 0b1011 # decimal 11
result = x | y # Bitwise or, result in decimal format
print(result)
print(bin(result)) # bin() function converts decimal to binary

## Proof
## 1110
## 1011
## ----
## 1111
# 4. Decision statements
Find the largest two integers
/# Read two numbers
number1 = int(input("Enter the first number: "))
number2 = int(input("Enter the second number: "))

# Choose the larger number
if (number1 > number2):
    larger_number = number1
else:
    larger_number = number2

# Print the result
print("The larger number is:", larger_number)
Nested conditional statements
x = 10

if x > 5:  # True
    if x == 6:  # False
        print("nested: x == 6")
    elif x == 10:  # True
        print("nested: x == 10")
    else:
        print("nested: else")
else:
    print("else")
# 5. Problem-solving
## a. Find the largest three integers just using if statements. Take user inputs and display the result.
```python
num1 = int(input("Enter first number: "))
num2 = int(input("Enter second number: "))
num3 = int(input("Enter third number: "))

if num1 >= num2 and num1 >= num3:
    print("The largest number is:", num1)

if num2 >= num1 and num2 >= num3:
    print("The largest number is:", num2)

if num3 >= num1 and num3 >= num2:
    print("The largest number is:", num3)
```

## b. Identify multiple methods to determine if a number is even or odd. The user will input an integer, and the output will indicate whether it's "odd" or "even." The code should be organized into sections, with comments separating each part. For example
#######################
# Approach 1
#######################
# Approach 2
#######################
# Approach 3
#######################
```python
number = int(input("Enter an integer: "))

# Approach 1
#############################
if number % 2 == 0:
    print("even")
else:
    print("odd")

# Approach 2
#############################
if number / 2 == int(number / 2):
    print("even")
else:
    print("odd")

# Approach 3
#############################
if not (number % 2 != 0):
    print("even")
else:
    print("odd")
```
## c. Implement the grading scheme for the CISC 179 course. The grading scheme as follows:
Grade
Percent
Description
A
>90
Work of genuinely superior quality.
B
80-89
Passing performance falls approximately in the upper distribution of passing grades.
C
71-79
Passing performance falls approximately in the center of the distribution of all passing grades.
D
65-70
Passing performance falls approximately in the lower distribution of passing grades.
F
<65
Failing performance that does not satisfy the basic requirements of the course and needs to be improved in significant ways.
The user inputs a percentage as an integer, and the output displays the corresponding grade along with a description. The logic uses if, elif, and else statements, with comments to clarify each part.
```python
score: int = int(input("Enter your percentage: "))
# A
if score > 90:
    print("A Work of genuinely superior quality")
# B
elif 80 <= score <= 89:
    print("B Passing performance falls approximately in the upper distribution of passing grades.")
# C
elif 71 <= score <= 79:
    print("C Passing performance falls approximately in the center of the distribution of all passing grades.")
# D
elif 65 <= score <= 70:
    print("D Passing performance falls approximately in the lower distribution of passing grades.")
# F
else:
    print("F Failing performance that does not satisfy the basic requirements of the course and needs to be improved in significant ways.")
```
## d. Write a code which takes and, or, not as an user input. Create a truth table by writing your expressions. Display the truth table using print() function. Research how the truth tables for logical operators are structured.
```python
op = input("Enter operator (and, or, not): ")

if op == "and":
    print("True and True:", True and True)
    print("True and False:", True and False)
    print("False and True:", False and True)
    print("False and False:", False and False)
elif op == "or":
    print("True or True:", True or True)
    print("True or False:", True or False)
    print("False or True:", False or True)
    print("False or False:", False or False)
elif op == "not":
    print("not True:", not True)
    print("not False:", not False)
else:
    print("Invalid operator")
```

## e. To determine whether an integer is even or odd using only a bitwise AND operator. the user will input an integer. Your code should utilize the bitwise AND operator to differentiate between even and odd numbers. Finally, use the print()function to display the result. Avoid using any modulus or remainder operators.
```num = int(input("Enter an integer: "))

if (num & 1 == 0):
    print("even")
else:
    print("odd")
```
# 6. Code revision
Revise the code using nested if, elif, and else statements, and add comments to clarify the logic.
name = input("What's your name? ")
time = int(input("What time is it? "))

if (time < 1200):
    print("Hi "+name + ", good morning!")
if (time < 1800):
    print("Hi "+name + ", good afternoon!")
if (time > 1800):
    print("Hi "+name + ", good evening!")

print("Good Bye")
```python
name: str = input("What's your name? ")
time = int(input("What time is it? "))

# Check time for greeting
if time < 1200:
    print("Hi " + name + ", good morning!")
else:
    if time < 1800:
        print("Hi " + name + ", good afternoon!")
    else:
        print("Hi " + name + ", good evening!")

print("Good Bye")
```
# 7. Output verification
What will be the output of the code provided below without using Python?
```python
x = 1
y = 1.0
z = "1"

if x == y:
    print("one")
if y == int(z):
    print("two")
elif x == y:
    print("three")
else:
    print("four")
```
one,two
Please execute the code provided above in Python to confirm your result.
one
two

Process finished with exit code 0
# Challenges
Please describe the challenges you faced during the exercise.
## Figuring out how to write three separate if statements for the largest of three numbers without them interfering with each other.

## Keeping the upper and lower bounds straight in the grading scale chain so numbers wouldn't fall through the cracks.

## _________________________________________________________________________________________________

## _________________________________________________________________________________________________

## _________________________________________________________________________________________________

## _________________________________________________________________________________________________
# End of exercise
