## Python Basics
<a href="python">Back</a>

#### Print Statement with Different Value Types
This format is different from Python 2 which doesn't use parentheses.
```python
ndays= 365
print('There are', ndays, 'in a year')
```
#### Some Basic Syntaxes
```python
# Multi-line Statements
'''Hello,
World!'''

# Escape Characters
#  \n  newline
#  \t  tab position 8 char
#  \'  single quote mark
#  \"  double quote mark
#  \\  backslash character

#  Example - Prints each on newline
print('One\nTwo\nThree')

# Suppressing Newline
print('one', end=' ')

# Item Separator = None
print('one', sep='')

# Item Separator = Replace
print('one','two', sep='*')
```
#### Integer and Floating Points
```python
int('365') # convert string to integer

str(365) # covert integer to string

num = int(input('Enter a number: ')) # whole number / no decimal

num = float(input('Enter a number: ')) # real number / with decimal

# Store data within variables
sales = int(15)
commission = float(50.0)

# Multiply and assign variable
Tcommission = sales * commission
```
#### Formatting the Specifier
Floating Point
```python
# ,  indicates formatted with a comma
# .2 precision (round up two decimal places)
# f specifies that the data type is floating-pt

print(format(12345.6789, ',.2f'))
# returns: 12,345.68

print('The gross pay is $', format(1354543.24387, ',.2f'), sep='')
# returns 'The gross pay is $1,354,543.24'
```
Floating Point - Percentage
```python
# number is multiplied by 100 & displayed with %
print(format(0.5, '%'))
# returns: 50.000000%

print(format(0.5, '.0%'))
# returns: 50%
```
Integers
```python
# use d as the type designator
# cannot specify precision

print(format(123456, ',d'))
# returns 123456
```
#### Rational Operators
```python
>= # greater than or equal to
<= # less than or equal to
== # equal to
!= # not equal to
```
Checking numeric inside range with 'and'
```python
years = int(input('How many years? '))
if years >= 10 and years <= 19: 
      print('this is between 10 and 19)
else:
      print('this is not between 10 and 19')
```
Checking numeric outside range outside with 'or'
```python
years = int(input('How many years? '))
if years < 10 or years > 19: 
      print('this is outside of 10 and 19)
else:
      print('this is not outside of 10 and 19')
```
#### Short Answer Examples
Output “It is a Porsche” when the variable car contains the string “BoxsterS”.
```python
car = input('What type of car is it: ')
if car.lower() == 'boxsters': # entered using any case
    print('It is a Porsche')
else:
    print('It is not a Porsche')"
```
Output “Sufficient Quantity” when Instock variable is >=10 otherwise display “Time to Reorder”.
```python
instock = float(input('How much is in stock?: '))
if instock >= 10:
    print('Sufficient Quality')
else:
    print('Time to Reorder')
```
Assign the number 500 to the bonus variable when sales variable’s value is greater than or equal to 5000; otherwise, assign the number 100.
```python
sales = float(input('What did you make in sales: '))
if sales >= 5000:
    bonus = 500
else:
    bonus = 100
print('Your bonus is:', bonus)
```
Write a nested control structure that displays the following based on the values in the variables member and age.
- Member and 18 or older Display “You are old enough”
- Member and under 18 Display “You need an adult”
- Not a member Display “You need a membership”
```python
member = input('Are you a member? (Y/N): ')
if member.lower() == 'y':
    age = int(input('How old are you? ')) # Determine if user is old enough.
    if age >= 18:
        print('You are old enough.')
    else:
        print('You need an adult.')
else:
    print('You need a membership.')
```

Assign the appropriate value to the shipping variable; otherwise, assign 65 to the shipping variable.
- Hawaii - 100
- Oregon - 75
- Washington - 70
```python
state = input('What state are you shipping to? ')
if state.lower() == 'hawaii':
    shipping = 100
elif state.lower() == 'oregon':
    shipping = 75
elif state.lower() == 'washington':
    shipping = 70
else:
    shipping = 65
print('The shipping is:', shipping)
```
Assign the number .15 to the discount variable when the state variable contains the string “WA” and the sales variable contains a number that is less than 2000; otherwise, assign the number .25.
```python
state = input('Enter your state abbreviation: ')
sales = float(input('Enter your sales amount: '))
if state.lower() == 'wa' and sales <= 2000:
    discount = .15
else:
    discount = .25
print('Your discount is',discount)
```