### String
- ``word[0]`` # character in position 0
- ``word[-1]`` # last character
- ``word[-2]`` # second last character
- ``word[0:2]`` # characters from position 0 to 2
- ``word[4:]`` # characters from position 4 to the end
- ``word[-2:]`` # from second-last to the end
- ``word[:2] + word[4:]``
- ``len(s)``

### Lists
- ``squares = [1,2,3,4]``
- ``squares[0]`` # return 1
- ``squares[-3]:`` # return [2,3,4]
- ``squares[:]`` # return [1,2,3,4]
- ``squares + [5,6]`` # return [1,2,3,4,5,6]
- ``squares.append(123)`` # [1,2,3,4,5,6,123]
- ``letters = ['a','b','c']``
- ``letters[1:2]`` # remove item >> letters = ['a','c']
- ``len(letters) = 2``
- ``x = [['a','b'], [1,2,3]]``
- ``a,b = b,a+b``

### Control Flows
#### If
```python
x = int(input("Enter an integer: "))
if x < 0:
    # todo
elif x ==0:
    # todo
else:
    # todo
```
#### For
```python
for w in words:
    print(i, 'is a number')
    break
```
```python
for i in range(5):
    continue
```
#### Collections
````python
users = {'Han': 'active', 'Electron': 'inactive'}
# copy a collection
for user,status in users.copy().items():
    if status == 'active':
        del users[user]
````
#### Range
- ``list(range(5,8))`` # return [5,6,7]
- ``sum(range(4))`` # return 6
#### Pass
```python
while True:
    pass # pass does nothing

class EmptyClass:
    pass

``` 
#### Match
Similar to ``switch``
```python
def catch_error(status):
    match status: # python 3.10 above
        case 400 | 401 | 403:
            return "bad request"
        case _:
            return "nothing"

match point:
    case (0,0):
        print("Origin")
    case _:
        raise ValueError("Not a point")

class Point:
    x: int
    y: int
def where(point):
    match point:
        case Point(x=0, y=0):
            return "origin"
        case _:
            return "not a point"

match point:
    case [Point(x=0, y=0), Point(x=1,y=0)]:
        return "origin"
    case _:
        return "not a point"

match point:
    case Point(x=0, y=0) if x == y:
        return "origin"
    case _:
        return "not a point"

case [x,y,*rest]
```
#### Enum
```python
from enum import Enum
class Color(Enum):
    RED = 'red'

color = Color(input("Enter your choice of 'red':"))
match color:
    case Color.RED:
        print("I see red!")
```
#### Function
```python
def ask_ok(prompt, retries=4, reminder='something'):
    while True:
        ok = input(prompt)
        if ok in ('y','ye','yes',):
            return True
def f(a, L=None):
    if L is None:
        L = []
```
#### Generators
```python
# yield: return data and resume it
def reverse(data):
    for index in range(len(data) -1, -1, -1):
        yield data[index]
for char in reverse('golf'):
    print(char)
# print out f l o g
```
