# Meet Python <br><br><br>

---

## 1. collectionsTruthness

What will be the value of `res` after the following snippet is executed:

```python
xs = [()]
res = [False] * 2
if xs:
    res[0] = True
if xs[0]:
    red[1] = True
```

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```python
[True, False]
```

</details>

<br><br><br>

--- 

## 2. efficientComparison

You would like to write a function that takes integer numbers `x`, `y`, `L` and `R` as parameters, and returns `True` if `x`<sup>`y`</sup> lies within the interval `(L, R]` and `False` otherwise. You're considering several different ways to write the conditional statement inside this function:

1. `if L < x ** y <= R:`
2. `if x ** y > L and x ** y <= R:`
3. `if x ** y in range(L + 1, R + 1):`

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

Option `1` is the most optimal one.

</details>

<br><br><br>

--- 

## 3. specialConditional

Given two boolean variables `a` and `b`, one of the following statements works differently than the others. Which one is it?

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

`a == not b`

</details>

<br><br><br>

--- 

## 4. languageDifferences

Your friend is an experienced coder who just started learning Python. Since she is already proficient in Java and C++, she decided to write all of her snippets in all three languages, in order to ensure the Python code was working as expected. Here's the very first function your friend wrote in Python and Java (the C++ version is the same as Java one):

- Python:

```python
def division(x, y):
    return x // y
```

- Java:

```java
int division(int x, int y){
    return x / y;
}
```

You noticed that the functions aren't quite the same: they won't produce the same result for some valid values of `x` and `y`. For which of the following example inputs would these two versions produce different outputs?

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

`x = 15`, `y = -4`

</details>

<br><br><br>

---
 
## 5. countBits

Implement a function that, given an integer `n`, uses a specific method on it and returns the number of bits in its binary representation.

Note: in this task and most of the following tasks you will be given a code snippet with some part of it replaced by the ellipsis (`...`). Only this part is allowed to be changed.

### Example

For `n = 50`, the output should be

`countBits(n) = 6`.

`50`<sub>`10`</sub> = `11001`0<sub>`2`</sub>, a number that consists of `6` digits. Thus, the output should be `6`.

### Input/Output

- [execution time limit] 4 seconds (py)

- [input] integer n

    A positive integer.

    _Guaranteed constraints:_

`1 ≤ n ≤ 10`<sup>`9`</sup>.

- [output] integer

    The number of bits in binary representation of `n`.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```python
def countBits(n):
    return n.bit_length()
```

</details>

<br><br><br>

--- 

## 6. modulus

It frustrates you more than you'd like to admit that the modulus operator in Python can be applied to non-integer values. When you write code, you expect the result of the modulus operator to always be an integer, but thanks to Python this isn't always the case.

To fix this, you've decided to write your own modulus operator as a function. Your task is to implement a function that, given a number `n`, returns `-`1 if this number is not an integer and `n % 2` otherwise. It is guaranteed that if the number represents an integer, it will be written without a decimal point.

### Example

- For `n = 15`, the output should be

    `modulus(n) = 1`;

- For `n = 23.12`, the output should be

    `modulus(n) = -1`.

### Input/Output

- [execution time limit] 4 seconds (py)

- [input] numeric n

    A non-negative number that can be an `int`, a `float`, or a `long`.

    Guaranteed constraints:

    `0 ≤ n ≤ 1000`.

- [output] integer

    Return `n % 2` if `n` is an integer, otherwise return `-1`.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```python
def modulus(n):
    if isinstance(n, int):
        return n % 2
    else:
        return -1
```

</details>

<br><br><br>

--- 

## 7. simpleSort

To understand how efficient the built-in Python sorting function is, you decided to implement your own simple sorting algorithm and compare its speed to the speed of the Python sorting. Write a function that, given an array of integers `arr`, sorts its elements in ascending order.

_Hint: with Python it's possible to swap several elements in a single line. To solve the task, use this knowledge to fill in both of the blanks (`...`)._

### Example

For `arr = [2, 4, 1, 5]`, the output should be

`simpleSort(arr) = [1, 2, 4, 5]`.

### Input/Output

- [execution time limit] 4 seconds (py)

- [input] array.integer arr

    Guaranteed constraints:

    `1 ≤ arr.length ≤ 500`,

    `-10`<sup>`5`</sup>` ≤ arr[i] ≤ 10`<sup>`5`</sup>.

- [output] array.integer

    The given array with elements sorted in ascending order.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```python
def simpleSort(arr):

    n = len(arr)

    for i in range(n):
        j = 0
        stop = n - i
        while j < stop - 1:
            if arr[j] > arr[j + 1]:
                arr[j],arr[j+1] = arr[j+1],arr[j]
            j += 1
    return arr
```

</details>

<br><br><br>

--- 

## 8. baseConversion

Your university professor decided to have a little fun and asked the class to implement a function that, given a number `n` and a base `x`, converts the number from base `x` to base `16`. To make things more interesting, he announced that the first student to write the solution will have to answer fewer question than the rest of the class during the final exam.

Laughing devilishly, you asked if it was okay to use a language of your choice, and the unsuspecting professor answered "yes". It's settled then: Python is your language of choice!

Now you're bound to win. Implement a function that, given an integer number `n` and a base `x`, converts `n` from base `x` to base `16`.

### Example

For `n = "1302"` and `x = 5`, the output should be

`baseConversion(n, x) = "ca"`.

Here's why:

`1302`<sub>`5`</sub>` = 202`<sub>`10`</sub>` = ca`<sub>`16`</sub>.

### Input/Output

- [execution time limit] 4 seconds (py)

- [input] string n

    A valid non-negative integer in base `x`. The string is guaranteed to consist of digits and lowercase English letters.

    _Guaranteed constraints:_

    `1 < n.length ≤ 10`.

- [input] integer x

    The base of `n`.

    _Guaranteed constraints:_

    `2 ≤ x ≤ 36`.

- [output] string

The value of `n` in base `16`. The string should contain only digits and lowercase English letters `'a' - 'f'`.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```python
def baseConversion(n, x):
    return hex(int(n,x))[2::]
```

</details>

<br><br><br>

--- 

## 9. mexFunction

You've just started to study impartial games, and came across an interesting theory. The theory is quite complicated, but it can be narrowed down to the following statements: solutions to all such games can be found with the mex function. Mex is an abbreviation of minimum excludant: for the given set s it finds the minimum non-negative integer that is not present in `s`.

You don't yet know how to implement such a function efficiently, so would like to create a simplified version. For the given set `s` and given an `upperBound`, implement a function that will find its mex if it's smaller than `upperBound` or return `upperBound` instead.

_Hint: `for` loops also have an `else` clause which executes when the loop completes normally, i.e. without encountering any `break`s_

### Example

- For `s = [0, 4, 2, 3, 1, 7]` and `upperBound = 10`,

    the output should be

    `mexFunction(s, upperBound) = 5`.

    `5` is the smallest non-negative integer that is not present in `s`, and it is smaller than `upperBound`.

- For `s = [0, 4, 2, 3, 1, 7]` and `upperBound = 3`,

    the output should be

    `mexFunction(s, upperBound) = 3`.

    The minimum excludant for the given set is `5`, but it's greater than `upperBound`, so the output should be `3`.

### Input/Output

- [execution time limit] 4 seconds (py)

- [input] array.integer s

    Array of distinct non-negative integers.

    _Guaranteed constraints:_

    `0 ≤ s.length ≤ 100`,

    `0 ≤ s[i] ≤ 100`.

- [input] integer upperBound

    A positive integer.

    _Guaranteed constraints:_

    `1 ≤ upperBound ≤ 100`.

- [output] integer

    Mex of `s` if it's smaller than `upperBound`, or `upperBound` instead.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```python
def mexFunction(s, upperBound):
    found = -1
    for i in range(upperBound):
        if not i in s:
            found = i
            break
    else:
        found=upperBound

    return found
```

</details>

<br><br><br>

--- 

## 10. listBeautifier

Let's call a list beautiful if its first element is equal to its last element, or if a list is empty. Given a list `a`, your task is to chop off its first and its last element until it becomes beautiful. Implement a function that will make the given `a` beautiful as described, and return the resulting list as an answer.

_Hint: one of the features introduced in Python 3 called [extended unpacking](https://www.python.org/dev/peps/pep-3132/) could help here._

### Example

- For `a = [3, 4, 2, 4, 38, 4, 5, 3, 2]`, the output should be

    `listBeautifier(a) = [4, 38, 4]`.

    Here's how the answer is obtained:

    `[3, 4, 2, 4, 38, 4, 5, 3, 2]` => `[4, 2, 4, 38, 4, 5, 3]` => `[2, 4, 38, 4, 5]` => `[4, 38, 4]`.

- For `a = [1, 4, -5]`, the output should be

    `listBeautifier(a) = [4]`.

### Input/Output

- [execution time limit] 4 seconds (py3)

- [input] array.integer a

    A list of integers.

    _Guaranteed constraints:_

    `0 ≤ a.length ≤ 50`,

    `1 ≤ a[i] ≤ 100`.

- [output] array.integer

    A _beautiful_ list obtained as described above.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```python
def listBeautifier(a):
    res = a[:]
    while res and res[0] != res[-1]:
        a,*res,b= res
    return res
```

</details>

<br><br><br>

--- 
