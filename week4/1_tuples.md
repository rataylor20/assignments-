# CISC 179 - Week 4 assignment 1                
## Tuples
This assignment covers Python tuples 

## answers and code 
tuples
1a) Take five inputs from an user and save it in a tuple called my_tuple
``` python
my_tuple = tuple(input(f"Enter value {i+1}: ") for i in range(5))
print(my_tuple)
```

1b. How do you assign a single element in a tuple?
```python
my_tuple = (5,)
```
1c. my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)Count the repeated integers and print the result on the console.
```python
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)

print("1 count:", my_tuple.count(1))
print("2 count:", my_tuple.count(2))
print("3 count:", my_tuple.count(3))
print("4 count:", my_tuple.count(4))
print("5 count:", my_tuple.count(5))
```
1d. my_tuple = my_tuple + my_tuple
Proof that my_tuple in part c is different than the my_tuplein part d.
```python
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
print("ID before:", id(my_tuple))

my_tuple = my_tuple + my_tuple
print("ID after:", id(my_tuple))
```
1e. Explain why the following operations aren’t legal for the tuple. Answer without using the Python.
x = (1,2,3,4)   legal? 

x.append(1) Tuples don't have an append() function because they are immutable (fixed-size), so you can't add items to them after making them.

x[1] = "hello" Tuples do not support item assignment, meaning you can't swap or change elements once they are in place.

del x[2] You cannot delete individual items out of a tuple for the same reason they can't be modified.

2. Packing and unpacking tuples
Python permits tuples to appear on the left side of an assignment operator, in which case variables in the tuple receive the corresponding values from the tuple on the right side of the assignment operator. Here’s a simple example:
(one, two, three, four) =  (1, 2, 3, 4)
2a.Python has an extended unpacking feature, allowing an element marked with * to absorb any number of elem What is the data type of each variable? int
2b. ents not matching the other elements. For example,
x = (1, 2, 3, 4)
a, b, *c = x
a, b, c
(1, 2, [3, 4])
2c. What will be the result of a, *b, c = x?
```python
x = (1, 2, 3, 4)
a, *b, c = x
print(a, b, c)
```

3. Memory management
my_x = [100,200,300,400]
my_y = (200,300,400,500)

Discuss how memory addresses are assigned to each index of the list and the tuple. Pay attention to new addresses & re-used addresses.

Python uses the same memory address for 200, 300, and 400 since they're in both my_x and my_y, but 100 and 500 get their own unique addresses since they only show up once. Both collections just point to where those numbers are stored, so any numbers that match end up sharing the exact same ID.

| Index | my_x | my_y |
| :--- | :--- | :--- |
| 0 | new address for 100 | shared address for 200 |
| 1 | shared address for 200 | shared address for 300 |
| 2 | shared address for 300 | shared address for 400 |
| 3 | shared address for 400 | new address for 500 |



Challenges
Please describe the challenges you faced during the exercise.
honestly at this point my eyes are my biggest challenges 
