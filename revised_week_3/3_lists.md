# CISC 179 - Week 3
## Lists

This assignment covers Python Lists 

## code and answers 
# 1. Lists
## a. Using a range function, generate a list of 100 integers and assign the list to my_list. Verify that the variable my_listdata type is list. Use your favorite four methods and apply on the list. You can find the methods on Python Docs (https://docs.python.org/3/tutorial/datastructures.html).
```python
my_list = list(range(100))
print(type(my_list))
# my 4 methods 
my_list.append(100)
my_list.pop()
my_list.reverse()
my_list.sort()
```

## b. Suppose that you have a list of 10 items long. How might you move the last three items from the end of the list to the beginning, keeping them in the same order?
```python
items = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
items = items[-3:] + items[:-3]

print(items)
```

## c. What would be the result of len([[1,2]] * 3)? Try to do it without coding and then verify using Python.
3

Process finished with exit code 0

## d. Create a list my-list-ten of 10 items that includes some duplicate entries. Then, generate a second list my-list-ten-mem that contains the memory addresses of the items from the list my-list-ten. Use Python to research and identify the unique and duplicate memory addresses.
```python
my_list_ten = ["b58", "rb20", "sr20", "rb26", "2jz", "b58", "rb20", "sr20", "rb26", "2jz"]
my_list_ten_mem = []

for item in my_list_ten:
    my_list_ten_mem.append(id(item))

print(my_list_ten_mem)
```
## e. Delete the list my-list-ten created in the above step.
```python
del my_list_ten
```
## f. Create a new list my-new-list of the same 10 items used in my-list-ten. Generate memory addresses of the items in my-new-list and compare them with the memory addresses in my-list-ten-mem. Discuss what do you observe.
```python
my_new_list = ["b58", "rb20", "sr20", "rb26", "2jz", "b58", "rb20", "sr20", "rb26", "2jz"]
my_new_list_mem = []

for item in my_new_list:
    my_new_list_mem.append(id(item))

print(my_new_list_mem)
```
Even though I deleted the old list and made a brand new one, the memory addresses are still the exact same. Python just keeps the identical string objects in memory and points to them again instead of making new ones.
## g. Suppose that you have the following list:
x = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
What code could you use to get a copy y of that list in which you could change the elements without the side effect of changing the contents of x?
```python
x = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```
## h. Is it possible to use multiple expressions within a list comprehension?
No you can only have one main expression at the very front, but you can use multiple for loops or if checks in the same line.

## i. Using a list comprehension, count how many spaces are in the following statement.
"To be, or not to be, this is the question"
```python
statement = "To be, or not to be, this is the question"
spaces = [char for char in statement if char == " "]

print(len(spaces))
```
output= 9

Process finished with exit code 0
## j. Choose any 5 lists operations of your choice from the link Python Data Structures Documentation (https://docs.python.org/3/tutorial/datastructures.html).
```python
my_list = [1, 2, 3, 4, 5, 6]
my_list.pop()
my_list.insert(0, 0)
my_list.remove(3)
my_list.sort()
```
# Challenges
## Please describe the challenges you faced during the exercise.
Figuring out why the memory addresses stayed the same in section f even after deleting the old list—I didn't expect Python to reuse them like that.
