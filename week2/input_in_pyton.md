User input
a. Kilograms to Pounds

Write a program that prompts the user to enter the weight of a person in kilograms and outputs the equivalent weight in pounds.

Note: 1 kilogram = 2.2 pounds.

```python
kg = float(input("Enter weight in kilograms: "))
pounds = kg * 2.2
print("Equivalent weight in pounds:", pounds)
```
print("Hello World")

b. Credit Card Interest

Interest on a credit card's unpaid balance is calculated using the average daily balance. Suppose that netBalance is the balance shown in the bill, payment is the payment made, d1 is the number of days in the billing cycle, and d2 is the number of days payment is made before the billing cycle.

The average daily balance is:

averageDailyBalance = (netBalance × d1 - payment × d2) / d1 

If the interest rate per month is, say, 0.0152, then the interest on the unpaid balance is:

interest = averageDailyBalance × 0.0152 

Write a program that accepts as input netBalance, payment, d1, d2, and interest rate per month. The program outputs the interest.

```python
netBalance = float(input("Enter net balance: "))
payment = float(input("Enter payment amount: "))
d1 = float(input("Enter days in billing cycle (d1): "))
d2 = float(input("Enter days payment made before cycle (d2): "))
interestRate = float(input("Enter monthly interest rate: "))

averageDailyBalance = (netBalance * d1 - payment * d2) / d1
interest = averageDailyBalance * interestRate

print("The interest on the unpaid balance is:", interest)
```
c. Distance Between Two Cars

Two cars A and B leave an intersection at the same time. Car A travels west at an average speed of x miles per hour and car B travels south at an average speed of y miles per hour.

Write a program that prompts the user to enter the average speed of both cars and the elapsed time (in hours and minutes) and outputs the shortest distance between the cars.
```python
speed_a = float(input("Enter car A speed (mph): "))
speed_b = float(input("Enter car B speed (mph): "))
hours = float(input("Enter elapsed hours: "))
minutes = float(input("Enter elapsed minutes: "))
time_in_hours = hours + (minutes / 60)
dist_a = speed_a * time_in_hours
dist_b = speed_b * time_in_hours
distance = (dist_a**2 + dist_b**2) ** 0.5
print("Shortest distance between the cars:", distance, "miles")
```
Troubleshooting

Please troubleshoot the following issues without using Python, and explain your reasoning.

a. hello = "hello" Valid. Just a regular variable holding a string.

b. _var = 100 Valid. Python lets you start variable names with an underscore.

c. !var_1 = 200 Invalid. You can't start a variable name with special characters like an exclamation point.

d. print = "print me" Invalid / bad practice. It overrides the built-in print function, so you won't be able to use print() anymore in that script.

e. False = 0
Invalid. False is a reserved keyword in Python, so you can't name a variable that.
