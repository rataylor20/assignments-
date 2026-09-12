## CISC 171 - Week 2
## Programming Variables

## This Assignments covers Programming Variables

## code and answers



var1 = 10
print("Memory address of var1 (10):", hex(id(var1)))

var1 = 100
print("Memory address of var1 (100):", hex(id(var1)))

# EXPLANATION (:
# You should see two distinct addresses for var1. Explain why there are two different addresses and what happened to the first one:
# "Basically, when I changed var1 from 10 to 100, Python created a brand new integer object
# in memory for 100 and pointed var1 to it. The old 10 object is just sitting there in memory
# until Python cleans it up because nothing is referencing it anymore."


var2 = 300
# Check the memory address of var2. Did the python interpreter assign a new memory address or reuse the existing one?
print("Memory address of var2 (300):", hex(id(var2)))

# EXPLANATION:
# "It got a brand new memory address because 300 is outside of Python's small integer cache
# range (-5 to 256), so Python allocates a fresh spot in memory for it instead of reusing an existing one."


print("\n--- Memory Map (Strings & Characters) ---")

str1 = "hello"
str2 = "world"

print("h and e memory addresses:", hex(id(str1[0])), hex(id(str1[1])))

print("Character 'l' in str1 (index 2):", hex(id(str1[2])))
print("Character 'l' in str1 (index 3):", hex(id(str1[3])))
print("Character 'o' in str1 (index 4):", hex(id(str1[4])))

print("Character 'w' in str2 (index 0):", hex(id(str2[0])))
print("Character 'o' in str2 (index 1):", hex(id(str2[1])))
print("Character 'r' in str2 (index 2):", hex(id(str2[2])))
print("Character 'l' in str2 (index 3):", hex(id(str2[3])))
print("Character 'd' in str2 (index 4):", hex(id(str2[4])))


print("\n--- Problem-Solving ---")

x = "dog"
y = "cat"

# 1. x + y
# Answer: "dogcat"
print("x + y =", x + y)

# 2. "the" + x + " chases the" + y
# Answer: "thedog chases thecat"
print('Compound string:', "the" + x + " chases the" + y)

# 3. x * 4
# Answer: "dogdogdogdog"
print("x * 4 =", x * 4)



# Explanation
# a. hello = "hello" -> This is actually valid, it assigns the string "hello" to the variable hello.
# b. sun - ime -> Invalid because you can't use a hyphen (-) in a variable name; Python thinks you're trying to subtract.
# c. var_1 = 200 -> Valid, underscores are totally fine in variable names.
# d. print = "print me" -> Bad idea because 'print' is a built-in Python function keyword, so reassigning it breaks normal printing later.
# e. false = 0 -> Technically valid in Python since it's lowercase and Python is case-sensitive, but it's super confusing because 'False' (capital F) is a boolean.


# Challenges
# "Honestly, wrapping my head around how Python handles memory addresses and IDs was a bit tricky
# at first, especially seeing how small numbers vs larger numbers get stored differently.
# Also realizing you can't just add numbers to strings without getting a type error made sense
# once I saw what happened!"
