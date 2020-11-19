# Control Flow

***

### `while`:

```python
---------------------------------------------
# Fibonacci Series
>>> a, b = 0, 1
>>> while a < 1000:
...     print(a, end=',')
...     a, b = b, a+b
---------------------------------------------
```

***

### `if`:

```python
---------------------------------------------
>>> x = int(input("Please enter an integer: "))
Please enter an integer: 42
>>> if x < 0:
...     x = 0
...     print('Negative changed to zero')
... elif x == 0:
...     print('Zero')
... elif x == 1:
...     print('Single')
... else:
...     print('More')
...
More
--------------------------------------------
```

There can be zero or more [`elif`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../reference/compound_stmts.html#elif) parts, and the [`else`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../reference/compound_stmts.html#else) part is optional. The keyword ‘`elif`’ is short for ‘else if’, and is useful to avoid excessive indentation. An `if` … `elif` … `elif` … sequence is a substitute for the `switch` or `case` statements found in other languages.

***

***

### `for`:

- iterates over the items of any sequence (a list | a string), in the order that they appear in the sequence.

```python
---------------------------------------------
>>> words = ['cat', 'window', 'defenestrate']
>>> for w in words:
...     print(w, len(w))
...
cat 3
window 6
defenestrate 12
---------------------------------------------
```

- loop over a copy of the collection or to create a new collection:

```python
---------------------------------------------
#Strategy:  Iterate over a copy
for user, status in users.copy().items():
    if status == 'inactive':
        del users[user]

#Strategy:  Create a new collection
active_users = {}
for user, status in users.items():
    if status == 'active':
        active_users[user] = status
---------------------------------------------
```

***

***

### `range()`:

- generates arithmetic progressions:

```python
---------------------------------------------
>>> for i in range(5):
...     print(i)
...
0
1
2
3
4

# range(start, end)
# range(start, end, step)
# range(-10, -100, -30)
---------------------------------------------
```

- iterate over indices of sequence (_range() + len()_)

```python
---------------------------------------------
>>> a = ['Mary', 'had', 'a', 'little', 'lamb']
>>> for i in range(len(a)):
...     print(i, a[i])
...
0 Mary
1 had
2 a
3 little
4 lamb
---------------------------------------------
```

In most such cases, however, it is convenient to use the [`enumerate()`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../library/functions.html#enumerate "enumerate") function, see [Looping Techniques](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/datastructures.html#tut-loopidioms).

A strange thing happens if you just print a range:


```
>>> print(range(10))
range(0, 10)
```

In many ways the object returned by [`range()`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../library/stdtypes.html#range "range") behaves as if it is a list, but in fact it isn’t. It is an object which returns the successive items of the desired sequence when you iterate over it, but it doesn’t really make the list, thus saving space.

We say such an object is [iterable](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../glossary.html#term-iterable), that is, suitable as a target for functions and constructs that expect something from which they can obtain successive items until the supply is exhausted. We have seen that the [`for`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../reference/compound_stmts.html#for) statement is such a construct, while an example of function that takes an iterable is [`sum()`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../library/functions.html#sum "sum"):


```
>>> sum(range(4))  # 0 + 1 + 2 + 3
6
```

Later we will see more functions that return iterables and take iterables as arguments. Lastly, maybe you are curious about how to get a list from a range. Here is the solution:


```
>>> list(range(4))
[0, 1, 2, 3]
```

In chapter [Data Structures](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/datastructures.html#tut-structures), we will discuss in more detail about [`list()`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../library/stdtypes.html#list "list").

***

### `break` && `continue`:

- _break_ : breaks out of the loop
- _continue_ : continues with next iteration of the loop

```python
---------------------------------------------
>>> for n in range(2, 10):
...     for x in range(2, n):
...         if n % x == 0:
...             print(n, 'equals', x, '*', n//x)
...             break
...     else:
...         print(n, 'is a prime number')
---------------------------------------------
```

When used with a loop, the `else` clause has more in common with the `else` clause of a`try` statement than it does with that of`if` statements: a `try` statement’s `else` clause runs when no exception occurs, and a loop’s `else` clause runs when no `break` occurs. 

```python
---------------------------------------------
>>> for num in range(2, 10):
...     if num % 2 == 0:
...         print("Found an even number", num)
...         continue
...     print("Found a number", num)
---------------------------------------------
```

***

***

### `pass`:

- _pass_ : syntactic requirements without action
  + placeholder for (functions | conditionals)
  + silently ignored.

```python
---------------------------------------------
>>> while True:
...     pass  # Busy-wait for keyboard interrupt 

>>> class MyEmptyClass: #creating minimal classes
...     pass

>>> def initlog(*args):
...     pass   # Remember to implement this!
---------------------------------------------
```

***
