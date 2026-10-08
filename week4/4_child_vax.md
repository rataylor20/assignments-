# CISC 179 - Week 4 assignment 4                   
## Nested dictionaries

This assignment covers Python Nested Dictionaries to find Patient Vax records.

## code and answers 
```python
# make an empty dictionary for patients
patient = {}

# start our record number at 1
count = 1

# function to add a patient
def insert(first, last, month):
    global count
    
    # put the info into a nested dictionary
    patient[count] = {
        "first_name": first,
        "last_name": last,
        "birth_month": month
    }
    
    # go to the next number for the next patient
    count = count + 1

# add first patient
insert("John", "Doe", 5)

# add second patient so it doesn't overwrite the first one
insert("Jane", "Smith", 8)

# print it out to make sure both are there
print(patient)
```
## output from code
{1: {'first_name': 'John', 'last_name': 'Doe', 'birth_month': 5}, 2: {'first_name': 'Jane', 'last_name': 
'Smith', 'birth_month': 8}}

Process finished with exit code 0

## Challenges 
1. It took a minute to figure out how to make sure each new patient got their own unique number key so it didn't just overwrite the first person I entered.


2. Trying to get all the curly braces and quotes lined up right when putting a dictionary inside another dictionary was a bit confusing at first.

3. Remembering to use the global keyword so the counter would actually update outside of the function took some trial and error.
   
