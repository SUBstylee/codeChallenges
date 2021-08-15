# The Journey Begins <br><br><br>

---
## 1. add

Write a function that returns the sum of two numbers.

### Example

For `param1 = 1` and `param2 = 2`, the output should be
`add(param1, param2) = 3`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer param1

    Guaranteed constraints:

    `-1000 ≤ param1 ≤ 1000`.

- [input] integer param2

    Guaranteed constraints:

    `-1000 ≤ param2 ≤ 1000`.

- [output] integer

    The sum of the two inputs.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function add(param1, param2) {
    return param1 + param2;
}
```

</details>

<br><br><br>

--- 

## 2. centuryFromYear

Given a year, return the century it is in. The first century spans from the year 1 up to and including the year 100, the second - from the year 101 up to and including the year 200, etc.

### Example

- For year = 1905, the output should be

    centuryFromYear(year) = 20;
- For year = 1700, the output should be

    centuryFromYear(year) = 17.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer year

    A positive integer, designating the year.

    _Guaranteed constraints:_

    `1 ≤ year ≤ 2005.`

- [output] integer

    The number of the century the year is in.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function centuryFromYear(year) {
    let century = 0;
    while (year > 0){
        year-=100;
        century+=1;
    }
    return century;
}
```

</details>

<br><br><br>

---

## 3. checkPalindrome

Given the string, check if it is a palindrome.

### Example

- For `inputString = "aabaa"`, the output should be

    `checkPalindrome(inputString) = true`;

- For `inputString = "abac"`, the output should be

    `checkPalindrome(inputString) = false`;

- For `inputString = "a"`, the output should be

    `checkPalindrome(inputString) = true`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] string inputString

    A non-empty string consisting of lowercase characters.

    _Guaranteed constraints:_

    `1 ≤ inputString.length ≤ 10^5`.

- [output] boolean

    `true` if `inputString` is a palindrome, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function checkPalindrome(inputString) {
    let rex = /[\W_]/g;
    let lowRegStr = inputString.toLowerCase().replace(rex, '');
    let reversed = lowRegStr.split('').reverse().join(''); 
    return reversed === lowRegStr;
}
```

</details>

<br><br><br>

---
