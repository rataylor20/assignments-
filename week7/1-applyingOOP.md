# CISC 179 - Week 7
## Applying OOP

This assignment covers Python object oriented programing concepts 

## code and answers 
# 1. Extending Stack Class Behavior
--- 1. CountingStack Output ---
100
```python
class Stack:
    def __init__(self):
        self.__stk = []

    def push(self, val):
        self.__stk.append(val)

    def pop(self):
        val = self.__stk[-1]
        del self.__stk[-1]
        return val


class CountingStack(Stack):
    def __init__(self):
        super().__init__()
        self.__counter = 0

    def get_counter(self):
        return self.__counter

    def pop(self):
        val = super().pop()
        self.__counter += 1
        return val


print("--- 1. CountingStack Output ---")
stk = CountingStack()
for i in range(100):
    stk.push(i)
    stk.pop()
print(stk.get_counter())  # Expected output: 100
print()
```
# 2a. Implementing a Queue Class from Scratch
--- 2a. Queue Output ---
1
dog
False
Queue error
```python
class QueueError(IndexError):
    pass


class Queue:
    def __init__(self):
        self.__queue = []

    def put(self, elem):
        self.__queue.insert(0, elem)

    def get(self):
        if len(self.__queue) == 0:
            raise QueueError()
        return self.__queue.pop()


print("--- 2a. Queue Output ---")
que = Queue()
que.put(1)
que.put("dog")
que.put(False)
try:
    for i in range(4):
        print(que.get())
except QueueError:
    print("Queue error")
print()
```
# 2b. Extending a Queue Class Capability
```python
class SuperQueue(Queue):
    def isempty(self):
        return len(self._Queue__queue) == 0


print("--- 2b. SuperQueue Output ---")
que = SuperQueue()
que.put(1)
que.put("dog")
que.put(False)
for i in range(4):
    if not que.isempty():
        print(que.get())
    else:
        print("Queue empty")
print()
```
# 3. Timer Class
--- 3. Timer Output ---
23:59:59
00:00:00
23:59:59

```python
def format_two_digits(val):
    return f"{val:02d}"


class Timer:
    def __init__(self, hours=0, minutes=0, seconds=0):
        self.__hours = hours
        self.__minutes = minutes
        self.__seconds = seconds

    def __str__(self):
        h = format_two_digits(self.__hours)
        m = format_two_digits(self.__minutes)
        s = format_two_digits(self.__seconds)
        return f"{h}:{m}:{s}"

    def next_second(self):
        self.__seconds += 1
        if self.__seconds == 60:
            self.__seconds = 0
            self.__minutes += 1
            if self.__minutes == 60:
                self.__minutes = 0
                self.__hours += 1
                if self.__hours == 24:
                    self.__hours = 0

    def prev_second(self):
        self.__seconds -= 1
        if self.__seconds < 0:
            self.__seconds = 59
            self.__minutes -= 1
            if self.__minutes < 0:
                self.__minutes = 59
                self.__hours -= 1
                if self.__hours < 0:
                    self.__hours = 23


print("--- 3. Timer Output ---")
timer = Timer(23, 59, 59)
print(timer)
timer.next_second()
print(timer)
timer.prev_second()
print(timer)
print()
```
# 4. Weeker Class
--- 4. Weeker Output ---
Mon
Tue
Sun
Sorry, I can't serve your request.

Process finished with exit code 0

```pyton
class WeekDayError(Exception):
    pass


class Weeker:
    __DAYS = ("Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun")

    def __init__(self, day):
        if day not in self.__DAYS:
            raise WeekDayError()
        self.__current_index = self.__DAYS.index(day)

    def __str__(self):
        return self.__DAYS[self.__current_index]

    def add_days(self, n):
        self.__current_index = (self.__current_index + n) % 7

    def subtract_days(self, n):
        self.__current_index = (self.__current_index - n) % 7


print("--- 4. Weeker Output ---")
try:
    weekday = Weeker('Mon')
    print(weekday)
    weekday.add_days(15)
    print(weekday)
    weekday.subtract_days(23)
    print(weekday)
    weekday = Weeker('Monday')
except WeekDayError:
    print("Sorry, I can't serve your request.")
```
# Challenges
1. Messing up indentation and missing colons on my if statements and def lines when typing out the methods.
2. PyCharm showing a typo warning for isempty(), but keeping it spelled that way because the assignment prompt specifically required that exact method name.
3. Accidentally using a single = instead of == in my if checks when trying to compare values.
