---
title: "Control Structure"
teaching: 20
exercises: 0
questions:
- "How do I use If Else structure?"
- "How do I use For Loop structure"
- "How do I use While Loop structure"

objectives:
- "Write conditional statement with `if...else` and `elseif()`"
- "Write and understand `for()` loop"
keypoints:
- "Use `if` and `else`"
- "Use `for` loop "
---

## if-else

_Syntax:_

**if**
```python
if (condition):
   do task
```

_Example_:

```python
a = 5
if (a>3):
   print("a is bigger than 3")
```

**if...else**

_Syntax_

```python
if (condition1):
   do task 1
else:
   do the rest
```

_Example_

```python
a = 2
if (a>3):
   print("a is bigger than 3")
else:
   print("a is NOT bigger than 3")
```

**if...elif...else**

_Syntax_

```python
if (condition1):
   do task 1
elif (condition2):
   do task 2
else:
   do the rest
```

_Example_

```python
a =2
if (a>3):
   print("a is bigger than 3")
elif (a==3):
   print("a equals to 3")
else:
   print("a is less than 3")

```


## For Loop

_Syntax_

```python
for (iterator in sequence):
    do task
}
```

_Example_
```python
for i in range(1,5):
    print(i)
```

## While Loop

_Syntax_

```python
while (this condition is true):
      do a thing
      increase in step

```

_Example:_
```python
a=1
while (a<5):
       print(a)
       a+=1
```

