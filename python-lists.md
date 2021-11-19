## Python Lists and Tuples
<a href="python">Back</a>

### Syntax Review
```python
# List Syntax
empty_list = []
empty_list = list()
list = [1,2,3]

# Tuple Syntax
empty_tuple = ()
empty_tuple = tuple()
tuple = (1,2,3,4)

# Set Syntax
empty_set = set()
variable_name=set(['a','b','c','d'])

# Dictionary Syntax
empty_dictionary={}
empty_dictionary = dict()
variable_name = {'keyname':'value','keyname':'value'}

# Check the class type of a variable.
print(type(variable_name))
```

### Lists
```python
 _items_in_list = len(listname)
access_values_in_list = print(listname[0]) 
# index 0 is the starting value. 
# This can be negative if you want to start from end
access_range_of_values = print(listname[0:2]) # This is called Slicing
# this would return all values from beginning not including 2
# listname[:2] would return same results
# listname[2:] would start index at position 2 and go through end
listname.append(item)
#The append() method adds an item to the end of the list.

listname1 = [1,2,3]
listname2 = []
for item in listname1:
    listname2.append(item)
    # makes a copy of a list

listname.extend(list2)
# adds a list onto an existing list. Not to be confused with append.

listname.remove('Math')
# removes 'math' item from the list

listname = [1,2,3,4,5]
del listname[2]
# the del statement deletes an item at a specific index location.

listname.insert(0,'Joe')
# Inserts Joe at position 0. The item that was there and all others are shifted
# 1 position towards the end.

listname.pop() 
    # .pop removes last item from a list
popped = courses.pop() 
    # returns the value it removed | you'd do print(popped)
listname.reverse()
    # reverses the list
listname.sort()
    # sorts by assending order - alterate original
listname.sort(reverse=True)
    # sorts by descending order - alterates original
sortedlist = sorted(listname)
    # using sorted this way prevents alterating the orginal list

print(min(listname)) # retreives minimum value in list
print(max(listname)) # retreives max value in list
print(sum(listname)) # retreives sum of list

find_index_of_item = print(listname.index('Art')) # returns index position of value
get_true_or_false = print('Math' in listname) # use in method to find if value exists

# See index of items while looping throug items in list:
for index, item in enumerate(listname):
    print(index,value)
    # if you don't want to start at index 0, pass through a 
    # starting value as an argument:
    for index, item in enumerate(listname, start=1):
        print(index,value)

# Turn list into a comma separated list of values:
list_str = ', '.join(listname) # join method does this - include space.

# To reverse this:
list_str_reverse = list_str.split(', ') # removes all of the commas & spaces.

# Flatten a nested list - flatten two-dimensional list.
grid = [[4,9,2],[3,5,7],[8,1,6]] # the given two-dimensional list.
flat_list = [item for l in grid for item in l] # unnest the list.
# results will be flat_list = [4,9,2,3,5,7,8,1,6]
```
### Tuples
```python
# tuples are immutable - can't be changed.
tuple_lists = (1,2,3,4) # parenthesis
```
### Converting between Lists and Tuples
```python
# Convert tuple to list:
number=(1,2,3)
number_list = list(number)

# Convert list to tuple:
number = ['one','two','three']
number_tuple = tuple(number)
```
### List Code Blocks
```python
# Passing a list as an argument to a function
def main_example():
    numbers = [1,2,3,4,5]
    print('Total:', get_totals(numbers))

def get_totals(value_list):
    total = 0
    for num in value_list:
        total += num
    return total

main_example()
```
## Python Lists and Files
### Writelines Method
```python
# Writelines method writes an entire list to a file and
# doesn't add a newline ('\n') at the end of each item.

# use the for loop to iterate through the list

cities = ['New York', 'Boston', 'Atlanta', 'Dallas']
outfile = open('cities.txt', 'w')
for item in cities:
    outfile.write(item + '\n')
outfile.close()
```
### Read Items from a File to a List
```python
infile = open('studenttest.txt', 'r')

# Read the contents of the file into a list.
student_test = infile.readlines()

# Close the file.
infile.close()

# Strip newline character from list.
index = 0
while index < len(student_test):
    student_test[index] = student_test[index].rstrip('\n')
    index += 1

# student_test list is now good to go.
```
### Two Dementional Lists
```python
grid = [[1,2,3],[4,5,6],[7,8,9]]

# to reference the elements in the list:
#        col 0:     col 1:     col 2:
# row 0: grid[0][0] grid[0][1] grid[0][1]
# row 1: grid[1][0] grid[1][1] grid[1][2]
# row 2: grid[2][0] grid[2][1] grid[2][2]

# sum all values in first row.
base_row = int(grid[0][0]) + int(grid[0][1]) + int(grid[0][2])
```
### Example of iterating through rows then columns to check values:
```python
def is_row_sum(grid, base_row, 3, 3): # Determine if row sums are equal.
    rowSum = 0
    for rowIndex in range(3): # iterated horizontally, rows to columns.
        for colIndex in range(3):
            rowSum += grid[colIndex][rowIndex] 
        if rowSum != base_row: # compare each row to base sum.
            return False
        else:
            rowSum = 0

    return True
```
### Example of iterating through columns then rows to check values:
```python
def is_col_sum(grid, base_row, 3, 3):
colSum = 0
for colIndex in range(3): # iterated vertically, columns to rows.
    for rowIndex in range(3):
        colSum += grid[rowIndex][colIndex]
    if colSum != base_row:
        return False
    else:
        colSum = 0

return True
```