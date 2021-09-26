# Python Style Guide

## Naming Conventions

### Package and Module Names

Packages and modules should be short, descriptive, and all lowercase names. For modules, you may use underscores for multi word names if needed. Do no use underscores in package names.

### Class Names

Class names should use the CapWords convention.

```python
# bad
class Example_class:
   ###

# good
class ExampleClass:
    ###
```

### Function And Variable Names

Function and variable names should be lowercase and may use underscores to join words for improved readability. Do not use camel case.

```python
# bad
def addNumbers():
	firstNum = 5
	secondNum = 7
	addedNum = 12

# good
def add_numbers():
	## notice shortening names for brevity
	num1 = 5
	num2 = 7
	result = 12
```





## Variable Type Annotations

Use the following rules for type annotation:

* Annotations for module level variables, class and instance variables, and local variables should have a single space after the colon.
* There should be no space before the colon.
* If an assignment has a right hand side, then the equality sign should have exactly one space on both sides:

```python
# bad
code:int  # No space after colon
code : int  # Space before colon

class Test:
    result: int=0  # No spaces around equality sign
   
# good
code: int
    
class Point:
    coords: Tuple[int, int]
    label: str = '<unknown>'
```





##     Miscellaneous Conventions

* Always convert tabs to spaces. A single tab should default to 4 spaces.

* Use the `is not` operator instead of `not is`. 

  ```python
  # bad
  if not foo is None:
  	###
  
  # good
  if foo is not None: 
  	###
  ```

* When working with try/catch blocks, always use a specific exception instead of the generic except clause.

  ```python
  # bad
  try: 
  	###
  except Exception:
  	###
  
  # good
  try:
  	###
  except ValueException:
  	###
  ```

* "Be consistent in return statements. Either all return statements in a function should return an expression, or none of them should."

  ```python
  # bad
  def foo(x):
      if x >= 0:
          return math.sqrt(x)
  
  def bar(x):
      if x < 0:
          return
      return math.sqrt(x)
      
  # good
  def foo(x):
      if x >= 0:
          return math.sqrt(x)
      else:
          return None
  
  def bar(x):
      if x < 0:
          return None
      return math.sqrt(x)
  ```

* Use`isinstance()` for object type comparisons

  ```python
  # bad
  if type(obj) is type(1):
  	###
  
  # good
  if isinstance(obj, int):
  	###
  ```

* "For sequences, (strings, lists, tuples), use the fact that empty sequences are false:"

  ```python
  # bad
  if len(seq):
      ###
  if not len(seq):
      ###
      
  # good
  if not seq:
  	###
  if seq:
  	###
  ```

* "Don't compare boolean values to True or False using `==`:"

  ```python
  # bad
  if greeting == True:
      ###
      
  # good
  if greeting:
      ###
  ```





## References

[1](https://www.python.org/dev/peps/pep-0008/#naming-conventions) PEP 8 -- Style Guide