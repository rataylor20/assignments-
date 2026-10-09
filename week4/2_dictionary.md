# CISC 179 - Week 4 assignment 2                  
## Dictionary
This assignment covers Python dictionaries 

## answers and code 

# 1A
```python
my_dict = {
    "name": "Ryan",
    "age": 32,
    "city": "san diego",
    "major": "cybersecurity",
    "car": "bmw",
    "pet": "dog",
    "branch": "navy",
    "hobby": "fishing",
    "sport": "baseball",
    "game": "icarus"
}

print(my_dict)
#results {'name': 'Ryan', 'age': 32, 'city': 'san diego', 'major': 'cybersecurity', 'car': 'bmw', 'pet': 'dog', 'branch': 'navy', 'hobby': 'fishing', 'sport': 'baseball', 'game': 'icarus'}
```
## 1B
```python
my_user_dict = {}
cont = "Y"

while cont == "Y" or cont == "y":
    k = input("Enter key: ")
    v = input("Enter value: ")
    my_user_dict[k] = v
    cont = input("Do you want to continue (Y/N): ")

print(my_user_dict)
```
## 1C
```python
data_list = [
    ('Name', 'Sarah Connor'),
    ('Date of birth', '1 Jan 1980'),
    ('Address', '1000 Black Mountain Drive', 92126),
    ('Name', 'Jim Hawkins')
]

my_clean_dict = {}

for item in data_list:
    if len(item) != 2:
        print("Invalid item length:", item)
    else:
        key = item[0]
        value = item[1]

        while key in my_clean_dict:
            print("Duplicate key found:", key)
            key = input("Enter a new key name: ")

        my_clean_dict[key] = value

print(my_clean_dict)
```
## 1D
```python
a = [("a", 1), ("b", 2), ("c", 3)]
new_dict = {}

for item in a:
    new_dict[item[0]] = item[1]

print(new_dict)
```
## 1E 
```python
text = "The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia. It has a powerful, muscular body with a large head and paws, a long tail and orange fur with black, mostly vertical stripes. It is traditionally classified into nine recent subspecies, though some recognise only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands."
words = text.split()
word_count = {}

for w in words:
    if w in word_count:
        word_count[w] += 1
    else:
        word_count[w] = 1

print(word_count)
# results: {'The': 1, 'tiger': 1, '(Panthera': 1, 'tigris)': 1, 'is': 2, 'a': 5, 'large': 2, 'cat': 1, 'and': 4, 'member': 1, 'of': 2, 'the': 3, 'genus': 1, 'Panthera': 1, 'native': 1, 'to': 1, 'Asia.': 1, 'It': 2, 'has': 1, 'powerful,': 1, 'muscular': 1, 'body': 1, 'with': 2, 'head': 1, 'paws,': 1, 'long': 1, 'tail': 1, 'orange': 1, 'fur': 1, 'black,': 1, 'mostly': 1, 'vertical': 1, 'stripes.': 1, 'traditionally': 1, 'classified': 1, 'into': 1, 'nine': 1, 'recent': 1, 'subspecies,': 2, 'though': 1, 'some': 1, 'recognise': 1, 'only': 1, 'two': 1, 'mainland': 1, 'Asian': 1, 'tigers': 2, 'island': 1, 'Sunda': 1, 'Islands.': 1}

Process finished with exit code 0

```
## 2A
```python
d_orig = {123: "coconut"}
d_copy = d_orig.copy()
d_copy[123] = "ryan"
print(d_orig)
print(d_copy)
```
## 2B
```python
d_orig = {123: "Coconut"}
d_copy = dict(d_orig)
d_copy[123] = "ryan"
print(d_orig)
print(d_copy)
```

## 2C
```python
d = {[123]: "Coconut"}
```

Python throws a TypeError because dictionaries need hashable keys, and lists are mutable so they're unhashable.
# Challenges 
1. Wrapping my head around memory references when just using = vs. .copy().

2. Figuring out why lists throw an unhashable error as keys.

3. Keeping track of how modifying a copied dict impacts the original one.
   








