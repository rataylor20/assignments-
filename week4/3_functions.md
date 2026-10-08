# CISC 179 - Week 4 assignment 4                   
## Functions

This assignment covers Python functions.

## code and answers
## 1A
```python
def convert_units(direction, *values):
    factor = 2.35215
    results = []

    for val in values:
        if direction == "kpl":
            converted = val * factor
            results.append(round(converted, 2))
        elif direction == "mpg":
            converted = val / factor
            results.append(round(converted, 2))

    return results
```
## 1B
```python
def print_reverse(*args):
    for item in reversed(args):
        print(item)
```
## 1C
Modifying a list or dictionary inside a function changes the original one outside of it because they are mutable. To stop that, you can pass a copy using .copy().

```python
def add_item(my_list):
    my_list.append(100)

numbers = [1, 2, 3]
add_item(numbers)
print(numbers)
```
## 1D 
funct_!() x stays 5

funct_2() becomes 2
## 2 
bug 1 change **c to *c

bug 2 add global x inside the function 

# Challenges 
 figuring out how *args handles random inputs
