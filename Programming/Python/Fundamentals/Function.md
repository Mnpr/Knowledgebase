***
### `Functions`:
#### Definition
- _def_ : definition
- parenthesised list of formal parameters
- """ _Documentation String_ """
```python
---------------------------------------------
# Fibonacci bis 100
def fib(n):
    """ List of Fibonacci series upto n """
    result = []
    a, b = 0, 1
    while a<n:
        result.append(a)
        a, b = b, a + b
    return result

f100 = fib(100)
print( f100 )
---------------------------------------------
```
- default return `None` (built-in name)
- Methods of different types may have the same name without causing ambiguity.
- The _execution_  function introduces a new symbol table used for the local variables of the function.
- Variable assignments in function store the value in the local symbol table.
- the global symbol table of built-in names.
- The _arguments_ to a function call are introduced in the local symbol table of the called function when it is called; thus, arguments are passed using _call by value_ , where  _value_ == an object _reference_
- When a function calls another function, a new local symbol table is created for that call.
- A function definition introduces the function name in the current symbol table. The value of the function name has a type that is recognised by the interpreter as a user-defined function. This value can be assigned to another name which can then also be used as a function. This serves as a general renaming mechanism:

```python
---------------------------------------------
>>> fib
<function fib at 10042ed0>
>>> f = fib
>>> f(100)
[0 1 1 2 3 5 8 13 21 34 55 89]
---------------------------------------------
```
***
#### Default Argument Values

```python
---------------------------------------------
def ask_ok(prompt, retries=4, reminder='Please try again!'):
    while True:
        ok = input(prompt)
        if ok in ('y', 'ye', 'yes'):
            return True
        if ok in ('n', 'no', 'nop', 'nope'):
            return False
        retries = retries - 1
        if retries < 0:
            raise ValueError('invalid user response')
        print(reminder)
---------------------------------------------
```

-  _in_ keyword 

The default values are evaluated at the point of function definition in the _defining_ scope.

```python
i = 5

def f(arg=i):
    print(arg)

i = 6
f() // `5`

```

**Important warning:** The default value is evaluated only once. This makes a difference when the default is a mutable object such as a list, dictionary, or instances of most classes. 

```python
def f(a, L=[]):
    L.append(a)
    return L

print(f(1)) # [1]
print(f(2)) # [1,2]
print(f(3)) # [1,2,3]

# the function accumulates the arguments passed to it on subsequent calls.
```
- don’t want the default to be shared between subsequent calls ?

```python
def f(a, L=None):
    if L is None:
        L = []
    L.append(a)
    return L

```

#### Keyword Arguments

- Functions calling using [keyword arguments](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../glossary.html#term-keyword-argument) of the form `kwarg=value`.

```python
def parrot(voltage, state='a stiff', action='voom', type='Norwegian Blue'):
    print("-- This parrot wouldn't", action, end=' ')
    print("if you put", voltage, "volts through it.")
    print("-- Lovely plumage, the", type)
    print("-- It's", state, "!")

```

- required argument (`voltage`) and three optional arguments (`state`, `action`, and `type`).
```python
parrot(1000)                                          # 1 positional argument
parrot(voltage=1000)                                  # 1 keyword argument
parrot(voltage=1000000, action='VOOOOOM')             # 2 keyword arguments
parrot(action='VOOOOOM', voltage=1000000)             # 2 keyword arguments
parrot('a million', 'bereft of life', 'jump')         # 3 positional arguments
parrot('a thousand', state='pushing up the daisies')  # 1 positional, 1 keyword

```

- In a function call, keyword arguments must follow positional arguments.
- invalid calls:

```python
parrot()                     # required argument missing
parrot(voltage=5.0, 'dead')  # non-keyword argument after a keyword argument
parrot(110, voltage=220)     # duplicate value for the same argument
parrot(actor='John Cleese')  # unknown keyword argument

```

- When a final formal parameter of the form `**name` is present, it receives a dictionary containing all keyword arguments except for those corresponding to a formal parameter.
- This may be combined with a formal parameter of the form `*name` which receives a [tuple](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/datastructures.html#tut-tuples) containing the positional arguments beyond the formal parameter list. (`*name` must occur before `**name`) 

```python
def cheeseshop(kind, *arguments, **keywords):
    print("-- Do you have any", kind, "?")
    print("-- I'm sorry, we're all out of", kind)
    for arg in arguments:
        print(arg)
    print("-" * 40)
    for kw in keywords:
        print(kw, ":", keywords[kw])

```
- call :

```python
cheeseshop("Limburger", "It's very runny, sir.",
           "It's really very, VERY runny, sir.",
           shopkeeper="Michael Palin",
           client="John Cleese",
           sketch="Cheese Shop Sketch")

```

- prints:

```
-- Do you have any Limburger ?
-- I'm sorry, we're all out of Limburger
It's very runny, sir.
It's really very, VERY runny, sir.
----------------------------------------
shopkeeper : Michael Palin
client : John Cleese
sketch : Cheese Shop Sketch

```

#### Special parameters

- By default, arguments may be passed to a Python function either by position or explicitly by keyword. For readability and performance, it makes sense to restrict the way arguments can be passed so that a developer need only look at the function definition to determine if items are passed by position, by position or keyword, or by keyword.

```python
def f(pos1, pos2, /, pos_or_kwd, *, kwd1, kwd2):
      -----------    ----------     ----------
        |             |                  |
        |        Positional or keyword   |
        |                                - Keyword only
         -- Positional only

```

where `/` and `*` are optional.

#### Positional-or-Keyword Arguments.
- If `/` and `*` are not present in the function definition, arguments may be passed to a function by position or by keyword.

#### Positional-Only Parameters

-  If _positional-only_, the parameters’ order matters, and the parameters cannot be passed by keyword. Positional-only parameters are placed before a `/`. The `/` is used to logically separate the positional-only parameters from the rest of the parameters. If there is no `/` in the function definition, there are no positional-only parameters.

Parameters following the `/` may be _positional-or-keyword_ or _keyword-only_.

#### Keyword-Only Arguments

To mark parameters as _keyword-only_, indicating the parameters must be passed by keyword argument, an `*` in the arguments list just before the first _keyword-only_ parameter.

#### Function Examples

```python
>>> def standard_arg(arg):
...     print(arg)
...
>>> def pos_only_arg(arg, /):
...     print(arg)
...
>>> def kwd_only_arg(*, arg):
...     print(arg)
...
>>> def combined_example(pos_only, /, standard, *, kwd_only):
...     print(pos_only, standard, kwd_only)

```

- The second function `pos_only_arg` is restricted to only use positional parameters as there is a `/` in the function definition:

```python
>>> pos_only_arg(1)
1

>>> pos_only_arg(arg=1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: pos_only_arg() got an unexpected keyword argument 'arg'

```

- The third function `kwd_only_args` only allows keyword arguments as indicated by a `*` in the function definition:

```python
>>> kwd_only_arg(3)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: kwd_only_arg() takes 0 positional arguments but 1 was given

>>> kwd_only_arg(arg=3)
3

```

And the last uses all three calling conventions in the same function definition:

```python
>>> combined_example(1, 2, 3)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: combined_example() takes 2 positional arguments but 3 were given

>>> combined_example(1, 2, kwd_only=3)
1 2 3

>>> combined_example(1, standard=2, kwd_only=3)
1 2 3

>>> combined_example(pos_only=1, standard=2, kwd_only=3)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: combined_example() got an unexpected keyword argument 'pos_only'

```

Finally, consider this function definition which has a potential collision between the positional argument `name` and `**kwds` which has `name` as a key:

```
def foo(name, **kwds):
    return 'name' in kwds

```

There is no possible call that will make it return `True` as the keyword `'name'` will always to bind to the first parameter. For example:

```
>>> foo(1, **{'name': 2})
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: foo() got multiple values for argument 'name'
>>>

```

But using `/` (positional only arguments), it is possible since it allows `name` as a positional argument and `'name'` as a key in the keyword arguments:

```
def foo(name, /, **kwds):
    return 'name' in kwds
>>> foo(1, **{'name': 2})
True

```

- The names of positional-only parameters can be used in `**kwds` without ambiguity.

#### Recap


As guidance:

*   Use positional-only if you want the name of the parameters to not be available to the user. This is useful when parameter names have no real meaning, if you want to enforce the order of the arguments when the function is called or if you need to take some positional parameters and arbitrary keywords.
    
*   Use keyword-only when names have meaning and the function definition is more understandable by being explicit with names or you want to prevent users relying on the position of the argument being passed.
    
*   For an API, use positional-only to prevent breaking API changes if the parameter’s name is modified in the future.
    

#### Arbitrary Argument Lists

- A function can be called with an arbitrary number of arguments, wrapped up in a tuple.

```python
def write_multiple_items(file, separator, *args):
    file.write(separator.join(args))

```

- These `variadic` arguments will be last in the list of formal parameters, because they scoop up all remaining input arguments that are passed to the function. Any formal parameters which occur after the `*args` parameter are ‘keyword-only’ arguments, meaning that they can only be used as keywords rather than positional arguments.

```python
>>> def concat(*args, sep="/"):
...     return sep.join(args)
...
>>> concat("earth", "mars", "venus")
'earth/mars/venus'
>>> concat("earth", "mars", "venus", sep=".")
'earth.mars.venus'

```

#### Unpacking Argument Lists

- The reverse situation occurs when the arguments are already in a list or tuple but need to be unpacked for a function call requiring separate positional arguments. For instance, the built-in [`range()`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../library/stdtypes.html#range "range") function expects separate _start_ and _stop_ arguments. If they are not available separately, write the function call with the `*`-operator to unpack the arguments out of a list or tuple:

```python
>>> list(range(3, 6))            # normal call with separate arguments
[3, 4, 5]
>>> args = [3, 6]
>>> list(range(*args))            # call with arguments unpacked from a list
[3, 4, 5]

```

Same way, dictionaries can deliver keyword arguments with the `**`-operator:

```python
>>> def parrot(voltage, state='a stiff', action='voom'):
...     print("-- This parrot wouldn't", action, end=' ')
...     print("if you put", voltage, "volts through it.", end=' ')
...     print("E's", state, "!")
...
>>> d = {"voltage": "four million", "state": "bleedin' demised", "action": "VOOM"}
>>> parrot(**d)
-- This parrot wouldn't VOOM if you put four million volts through it. E's bleedin' demised !

```

#### Lambda Expressions

- Anonymous functions created with the [`lambda`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../reference/expressions.html#lambda) keyword. lambda functions can reference variables from the containing scope:

```python
>>> def make_incrementor(n):
...     return lambda x: x + n
...
>>> f = make_incrementor(42)
>>> f(0)
42
>>> f(1)
43

```

The above example uses a lambda expression to return a function. Another use is to pass a small function as an argument:

>>>

```
>>> pairs = [(1, 'one'), (2, 'two'), (3, 'three'), (4, 'four')]
>>> pairs.sort(key=lambda pair: pair[1])
>>> pairs
[(4, 'four'), (1, 'one'), (3, 'three'), (2, 'two')]

```

#### Documentation Strings

```python
>>> def my_function():
...     """Do nothing, but document it.
...
...     No, really, it doesn't do anything.
...     """
...     pass
...
>>> print(my_function.__doc__)

```

#### Function Annotations

- Completely optional metadata information about the types used by user-defined functions ( [**PEP 3107**](https://www.python.org/dev/peps/pep-3107) and [**PEP 484**](https://www.python.org/dev/peps/pep-0484) more info).

- [Annotations](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../glossary.html#term-function-annotation) are stored in the `__annotations__` attribute of the function as a dictionary and have no effect on any other part of the function. Parameter annotations are defined by a colon after the parameter name, followed by an expression evaluating to the value of the annotation. Return annotations are defined by a literal `->`, followed by an expression, between the parameter list and the colon denoting the end of the [`def`](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../reference/compound_stmts.html#def) statement. The following example has a positional argument, a keyword argument, and the return value annotated:

```python
>>> def f(ham: str, eggs: str = 'eggs') -> str:
...     print("Annotations:", f.__annotations__)
...     print("Arguments:", ham, eggs)
...     return ham + ' and ' + eggs
...
>>> f('spam')
Annotations: {'ham': <class 'str'>, 'return': <class 'str'>, 'eggs': <class 'str'>}
Arguments: spam eggs
'spam and eggs'

```

#### Intermezzo: Coding Style

For Python, [**PEP 8**](https://www.python.org/dev/peps/pep-0008) has emerged as the style guide that most projects adhere to; it promotes a very readable and eye-pleasing coding style. Every Python developer should read it at some point; here are the most important points extracted for you:

*   Use 4-space indentation, and no tabs.
    
    4 spaces are a good compromise between small indentation (allows greater nesting depth) and large indentation (easier to read). Tabs introduce confusion, and are best left out.
    
*   Wrap lines so that they don’t exceed 79 characters.
    
    This helps users with small displays and makes it possible to have several code files side-by-side on larger displays.
    
*   Use blank lines to separate functions and classes, and larger blocks of code inside functions.
    
*   When possible, put comments on a line of their own.
    
*   Use docstrings.
    
*   Use spaces around operators and after commas, but not directly inside bracketing constructs: `a = f(1, 2) + g(3, 4)`.
    
*   Name your classes and functions consistently; the convention is to use `UpperCamelCase` for classes and `lowercase_with_underscores` for functions and methods. Always use `self` as the name for the first method argument (see [A First Look at Classes](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/classes.html#tut-firstclasses) for more on classes and methods).
    
*   Don’t use fancy encodings if your code is meant to be used in international environments. Python’s default, UTF-8, or even plain ASCII work best in any case.
    
*   Likewise, don’t use non-ASCII characters in identifiers if there is only the slightest chance people speaking a different language will read or maintain the code.
    
***

Actually, _call by object reference_ would be a better description, since if a mutable object is passed, the caller will see any changes the callee makes to it (items inserted into a list).
