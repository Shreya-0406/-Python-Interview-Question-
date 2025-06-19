# -Python-Interview-Question & Answers-
### 1.  Difference between list and Tuple in python?
## List
- List is mutable collection.
- After creating list changes can be done.
- List is created by using square brackets [].
- List occupy more spaces because of mutability.
## Tuple
- Tuple is immutable collection.
- After creating tuple changes cannot be done.
- Tuple is created by using parentheses ().
- Tuple occupy less spaces because of immutability.
## 2. How do set helps in removing duplicates from the list?
- Set does not allows duplicate values or elements.
- Only stores unique values.
- Converting a list into a set automatically removes duplicates.
``` python
list1=[10,20,30,30,40,50]
unique=list(set(list1))
print(unique) #0utput[10,20,30,40,50]
```
## 3. Why are dictionaries faster than lists for lookups?
### Dictionaries
- Dictionaries use a hash table in the background, which gives O(1) time complexity for lookups.
- When you store a key-value pair, the key is passed through a hash function.
- When you do a lookup, the dictionary hashes the key again and jumps directly to the memory location.
### List
- list uses linear search, which gives O(n) linear time for lookups.
- Lists don’t use keys, they store elements in order.
- To find a specific item, Python must check each element one by one.
## 4.How are python strings immutable if they allow operations like replace() ?
- An immutable object cannot be changed after it is created, but operations like replace() creates a new sting.
``` python
name = 'sreeya'
new_name = name.replace("ree","hre")
print(new_name) #output: shreya
```
## 5.How do you merge two dictionaries in python latest version?
- The pipe(|) operator merges the two dictionaries.
- A new dictionary is returned; dict1 and dict2 remain unchanged.
```python
dict1 = {'a': 1, 'b': 2}
dict2 = {'b': 3, 'c': 4}

merged = dict1 | dict2
print(merged) #output: {'a': 1, 'b': 3, 'c': 4}
```
## 6.Explain dictionary comprehension with example?
Dictionary comprehension lets you create a dictionary using a single line of code, using a similar syntax.
``` python
squares = {x: x**2 for x in range(1, 6)}
print(squares) #output:{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```
## 7.what are nested dictionaries and how do they you access inner values?
- Nested dictionaries is nothing but adding a dictionary as a value within a dictionary.
``` python
A = {'TEST 1':{'1st_inn':90,'2nd_inn':80},
      'TEST2':{'1st_inn':70,'2nd_inn':100}}
print(A) #output: {'TEST 1': {'1st_inn': 90, '2nd_inn': 80}, 'TEST2': {'1st_inn': 70, '2nd_inn': 100}}
```
## 8.How can you convert the list of tuples in to a dictionary?
- Each tuple in the list is treated as a (key, value) pair.
- The dict() constructor automatically converts the list into a dictionary.
``` Python
list = [('A', 1), ('B', 2)]
dict1 = dict(list)
print("Dictionary:", dict1)
```
## 9.how would you handle missing Key in a dictionary ?
- Use get() or defaultdict
``` python
my_dict = {"a": 1, "b": 2}

value = my_dict.get("c", 0)
print(value)  # Output: 0
```
## 10.can we use a list as a key in a dictionary? why and why not?
- No, we cannot use a list as a dictionary key in Python because lists are mutable and unhashable.
- Dictionary keys must be immutable and hashable.
## 11.what happens if you try add a mutable object to set?
- A set requires all its elements to be hashable and immutable.
- If we try to add a mutable it gets type error(unhashable type).
## 12.write a code to find common elements in two lists using set operations?
``` python
list1 = [1, 2, 3, 4, 5]
list2 = [4, 5, 6, 7, 8]

# Convert both lists to sets and use intersection
common_values = set(list1) & set(list2)
print("Common values:", common_values) #output:Common_values: {4, 5}
```
## 13.what is the difference between is and ==for string ? what is the syntax?
| Operator | Compares              | Checks for                              |
| -------- | --------------------- | --------------------------------------- |
| `==`     | **Value equality**    | Are the values the same?                |
| `is`     | **Identity equality** | Are they the **same object** in memory? |
``` python
a = "shreya"
b = "shreya"
print(a == b)  # Output: True
print(a is b)  # Output: True
```
## 14.How does sciling works in tuple and string? what are the syntax?
Slicing means extracting a portion  of a string or a tuple based on position.
Both strings and tuples are ordered and indexable, so slicing works the same way for both.
```python
str = "Python"
tup = (1, 2, 3, 4)
print(str[2:5])  # Output: "tho"
print(tup[:3])   # Output: (1, 2,3)
```
## 15. How can you reserve a string or list in python using sciling?
- Reverse a string or a list using slicing by using a negative step value.
- To reverse it:
- Start from the end of the sequence.
 - Move backward one item at a time.
 - This creates a reversed version of the original string or list.
  ``` python
 str= "python"
  list = [1, 2, 3]
  print(str[::-1])  # 'nohtyp'
  print(list[::-1])  # [3, 2, 1]
```
## 16. How would you optimize a recursive function to avoid maximum recursion depth errors in Python?
- To avoid maximum recursion depth errors in Python , you can optimize your recursive function in several ways, depending on    the problem.
### 1. Use Iteration Instead of Recursion:
- Rewrite the recursive function as an iterative one using loops(like for or while).
- Iteration avoids growing the call stack and is usually more memory-efficient.
``` python
# Recursive factorial (can hit recursion limit)
def factorial_recursive(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial_recursive(n - 1)
n = 5
print("Recursive Factorial of", n, "is", factorial_recursive(n))#OUTPUT: Recursive Factorial of 5 is 120
 # Iterative factorial
def factorial_iterative(n):
    result = 1
    for i in range(2, n + 1):
        result *= i
    return result
n = 5
print("Iterative Factorial of", n, "is", factorial_iterative(n)) #OUTPUT: Iterative Factorial of 5 is 120

```
### 2.Increase Recursion Limit:
- You can use sys.setrecursionlimit() to increase the recursion limit, but it's risky—going too high may cause a crash due      to stack overflow.
### 3. Use Memoization (Caching):
- For problems like Fibonacci where overlapping subproblems occur, memoization can reduce the number of recursive calls,       making the recursion shallow enough to avoid hitting the limit.
### 4. Use a Stack to Simulate Recursion:
- We can simulate recursion explicitly using a stack.
- When iteration isn't straightforward, we can use a stack.

## 17. What is the difference between *args and **kwargs in function definitions, and how do you handle both in a single           function?
- *args and **kwargs are powerful tools in Python used to pass a variable number of arguments to a function.
  ### *args:
  - Stands for “arbitrary positional arguments”.
  - Collects extra positional (non-keyworded) arguments.
  - Stored as a tuple.
``` python
def example_args(*args):
    for arg in args:
        print(arg)
example_args(1, 2, 3) #output: 1 ,2,3
```
### **kwargs:
- Stands for “arbitrary keyword arguments”.
- Collects extra keyword (named) arguments.
- Stored as a dictionary.
``` python
def example_kwargs(**kwargs):
    for key, value in kwargs.items():
        print(f"{key} = {value}")

example_kwargs(name="Alice", age=30) #output: name = Alice age = 30
```
### Using Both *args and **kwargs in a Single Function
You can combine both in one function — just to keep the order:
``` python
def combined_example(arg1, *args, **kwargs):
    print("arg1:", arg1)
    print("args:", args)
    print("kwargs:", kwargs)

combined_example("first", 10, 20, key1="value1", key2="value2")
#output:
arg1: first
args: (10, 20)
kwargs: {'key1': 'value1', 'key2': 'value2'}
```
## 18.Explain how closures work in Python. Give a real-time example where closures are better than classes.
- A closure is a function object that remembers values in enclosing scopes even if they are not in memory anymore.
### For a function to be a closure, three conditions must be met:
- A nested function (function inside another).
- The nested function references variables from the outer function.
- The outer function returns the nested function.
``` python
#Closure Version
def make_counter():
    count = 0
    def counter():
        nonlocal count
        count += 1
        return count
    return counter
c1 = make_counter()
print(c1())  # 1
print(c1())  # 2
print(c1())  # 3
```
```python
#Class Version
class Counter:
    def __init__(self):
        self.count = 0
    def __call__(self):
        self.count += 1
        return self.count
c2 = Counter()
print(c2())  # 1
print(c2())  # 2
```
## 19. When would you use a lambda function over a regular function in a production codebase?










  










    
