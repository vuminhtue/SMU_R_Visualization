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
Syntax:

**if**
```python
if (condition):
   do task
```

**if...else**
```python
if (condition1):
   do task 1
else:
   do the rest
```

**if...elif...else**
```python
if (condition1):
   do task 1
elif (condition2):
   do task 2
else:
   do the rest
```

**Examples**
if:
```python
a = 5
if (a>3):
   print("a is bigger than 3")
```

if else:

```python
a = 2
if (a>3):
   print("a is bigger than 3")
else:
   print("a is NOT bigger than 3")
```

if elif else

```python
a =2
if (a>3):
   print("a is bigger than 3")
elif (a==3):
   print("a equals to 3")
else:
   print("a is less than 3")
}
```


## For Loop

```python
for (iterator in sequence):
    do task
}
```

Example:
```python
for i in range(1,5):
    print(i)
```

## While Loop
Syntax
```python
while (this condition is true):
      do a thing
      increase in step

```

Example:
```python
a=1
while (a<5):
       print(a)
       a+=1
```

