# CISC 179 - Week 4 assignment 1                
## Tuples
This assignment covers Python tuples 

## answers and code 
tuples
1a) Take five inputs from an user and save it in a tuple called my_tuple
# Write your code here.
1b. How do you assign a single element in a tuple?
# Write your code here.
1c. my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)Count the repeated integers and print the result on the console.
# Write your code here.
1d. my_tuple = my_tuple + my_tuple
Proof that my_tuple in part c is different than the my_tuplein part d.
# Write your code here.
1e. Explain why the following operations aren’t legal for the tuple. Answer without using the Python.
x = (1,2,3,4)
x.append(1)
x[1] = "hello"
del x[2]
2. Packing and unpacking tuples
Python permits tuples to appear on the left side of an assignment operator, in which case variables in the tuple receive the corresponding values from the tuple on the right side of the assignment operator. Here’s a simple example:
(one, two, three, four) =  (1, 2, 3, 4)
2a. What is the data type of each variable?
2b. Python has an extended unpacking feature, allowing an element marked with * to absorb any number of elements not matching the other elements. For example,
x = (1, 2, 3, 4)
a, b, *c = x
a, b, c
(1, 2, [3, 4])
2c. What will be the result of a, *b, c = x?
# Write your code here.
3. Memory management
my_x = [100,200,300,400]
my_y = (200,300,400,500)
Discuss how memory addresses are assigned to each index of the list and the tuple. Pay attention to new addresses & re-used addresses.
Index
my_x
my_x
0
-
-
1
-
-
2
-
-
3
-
-
Challenges
Please describe the challenges you faced during the exercise.
# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________
