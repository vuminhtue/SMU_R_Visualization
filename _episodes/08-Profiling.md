---
title: "Profiling the code"
teaching: 10
exercises: 0
questions:
- "How to get the computed time for a chunk of code?"
- "How to profile the Python code"
objectives:
- "Learn time.time() function"
- "Learn Rprof() function"
keypoints:
- "time.time()"

---

## Computation time for a chunk of code
- Examine how much time is spent in programming's parts.
- Useful for optimization your code with parallel computation

```r
import time
start = time.time()

#Do the work
time.sleep(5)

stop = time.time()
print(stop-start, "second")
```

## cProfile
Python provides a built-in module to measure execution time and the module name is cProfile.It gives detailed report on time consumed by a program.

```python
import cProfile
  
cProfile.run("10 + 10")
```

For longer chunk of code which consisting of different function. We create a main function and run cProfile for that main function:

```python
import cProfile, time

def gosleep(a):
    time.sleep(a)
    
def printsomething(b):
    print(b)
    
def compute(c):
    return c**200
    
def main():
    gosleep(5)
    print("Hello")
    compute(100)

cProfile.run("main()")    
```



