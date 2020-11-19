### Numbers

***

- The operators `+`, `-`, `*` and `/`
  + (`/`) always returns a float.
  + floor division : //
  + exponent : ** || pow(x,y)
- Parentheses (`()`) : for grouping.

```python
print("""\
------------------------------------------------
Numbers Type: int, float,
                        decimal.Decimal (Decimal),
        fractions.Fraction (Fraction),
        3+5j (J | j suffix Complex Numbers)

                        - Floor division: // (discarding any fractional part) 
- ** : square
-  _ : last  printed expression ( I-mode >>> )

""")

>>> 17 // 3  # 5

>>> tax = 12.5 / 100
>>> price = 100.50
>>> price * tax
    12.5625
>>> price + _
                                         113.0625
>>> round(_, 2)
 113.06
```

- If variable !defined | (assigned a value):`NameError`

***

### Strings

***

- Enclosed in (`'...'`) || (`"..."`) 

- Immutable : `TypeError` << on assignment

- `\` :  escape

- + : Concatenation

- * : replication

- If !want `\` >>> `spChar` : _raw strings_ 

- _string literals_ next to each other : automatic concatenation =/= with literals & variables

- - `len()` : __built-in__ -> length of string

```python
---------------------------
>>> print(r'C:\some\name')
C:\some\name

>>> 'Py' 'thon'
'Python'

>>> s = 'supercalifragilisticexpialidocious'
>>> len(s) # 34
---------------------------
```

***

- _indexing_ : 0 - `len(str)` || `-1` - `[0]`

```python
print("""\
----------------------------

 +---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1

----------------------------
""")
```

- _slicing_ : to obtain >> `substring`
  - start included && end excluded
  - `s[:i(excluded)] + s[i(included):] ` == `s`
  - If index >>> too large : `IndexedError`

```python
-----------------------------
>>> word = 'Python'
>>> word[:x] + word[x:]
'Python'

>>> word[:x] # x : size of the string being sliced 
>>> word[42] # IndexError: string index out of range
>>> word[42:] # returns ''

------------------------------
```

***

### Lists

***

- _compound_ Homo/ Heterogeneous Collection
- __built-in__ _sequence_ types like Strings
  - indexed
  - sliced -> (list) : [shallow copy](file:///home/mnprterm/Downloads/browserDownloads/python-3.8.1-docs-html/tutorial/../library/copy.html#shallow-vs-deep-copy) of the list
- mutable
- `+` : concatenation
- `append()` 

```python
-----------------------------
>>> cubes = [1, 8, 27, 65, 125]
>>> cubes[3] = 64
>>> cubes.append(6 ** 3)
-----------------------------
```

- assignment to slices:
- __built-in__ _len()_

```python
-----------------------------
>>> letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> letters[2:5] = ['C', 'D', 'E'] # replace
>>> letters[2:5] = [] # remove
>>> len(letters) # 4
>>> letters[:] = [] # clear
-----------------------------
```

- nesting:

```python
-----------------------------
>>> alpha = ['a', 'b', 'c']
>>> nummeric = [1, 2, 3]
>>> alpha_numeric = [alpha, numeric] 
[['a', 'b', 'c'], [1, 2, 3]]
  _____________
 alpha_numeric[0]
>>> alpha_numeric[0][1] # b
-----------------------------
```

***
