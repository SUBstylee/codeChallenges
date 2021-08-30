# Smooth Sailing <br><br><br>

---

## 9. allLongestStrings

Given an array of strings, return another array containing all of its longest strings.

### Example

For `inputArray = ["aba", "aa", "ad", "vcd", "aba"]`, the output should be
`allLongestStrings(inputArray) = ["aba", "vcd", "aba"]`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.string inputArray

    A non-empty array.

    _Guaranteed constraints:_
    `1 ≤ inputArray.length ≤ 10`,
    `1 ≤ inputArray[i].length ≤ 10`.

- [output] array.string

    Array of the longest strings, stored in the same order as in the `inputArray`.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function allLongestStrings(inputArray) {
    return inputArray.sort((a, b) => b.length - a.length)
           .filter(m => m.length == inputArray[0].length)
}
```

</details>

<br><br><br>

--- 

## 10. comminCharacterCount

### **SOLUTION**

Given two strings, find the number of common characters between them.

### Example

For `s1 = "aabcc"` and `s2 = "adcaa"`, the output should be
`commonCharacterCount(s1, s2) = 3`.

Strings have `3` common characters `- 2` "a"s and `1` "c".

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] string s1

    A string consisting of lowercase English letters.

    _Guaranteed constraints:_
    `1 ≤ s1.length < 15`.

- [input] string s2

    A string consisting of lowercase English letters.

    _Guaranteed constraints:_
    `1 ≤ s2.length < 15`.

- [output] integer

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function commonCharacterCount(s1, s2) {
    let count = 0;
    const arr1=s1.split('');
    const arr2=s2.split('');
    for (let i=0;i<arr1.length;i++){
        const check=arr2.indexOf(arr1[i]);
        if(check!==-1){
            arr2.splice(check, 1);
            count++;
        }
    }
    return count;
}
```

</details>

<br><br><br>

--- 

## 11. isLucky

Ticket numbers usually consist of an even number of digits. A ticket number is considered lucky if the sum of the first half of the digits is equal to the sum of the second half.

Given a ticket number `n`, determine if it's lucky or not.

### Example

- For `n = 1230`, the output should be
`isLucky(n) = true`;
- For `n = 239017`, the output should be
`isLucky(n) = false`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer n

    A ticket number represented as a positive integer with an even number of digits.

    _Guaranteed constraints:_
    `10 ≤ n < 10`<sup>`6`</sup>.

- [output] boolean

    `true` if `n` is a lucky ticket number, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function isLucky(n) {
    const nums=String(n).split('')
    
    return nums.map(Number).reduce((a,b)=>a+b)/2 === nums.slice(0,String(n).length/2).map(Number).reduce((a,b)=>a+b);
}
```

</details>

<br><br><br>

--- 

## 12. sortByHeight

Some people are standing in a row in a park. There are trees between them which cannot be moved. Your task is to rearrange the people by their heights in a non-descending order without moving the trees. People can be very tall!

### Example

For `a = [-1, 150, 190, 170, -1, -1, 160, 180]`, 

the output should be

`sortByHeight(a) = [-1, 150, 160, 170, -1, -1, 180, 190]`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer a

    If `a[i] = -1`, then the `i`<sup>`th`</sup> position is occupied by a tree. Otherwise `a[i]` is the height of a person standing in the `i`<sup>`th`</sup> position.

    _Guaranteed constraints:_

    `1 ≤ a.length ≤ 1000`,
    `-1 ≤ a[i] ≤ 1000`.

- [output] array.integer

    Sorted array `a` with all the trees untouched.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function sortByHeight(a) {
    let heights=a.filter(h=>h!==-1);
    heights.sort((a,b)=>b-a);
    for(let i=0;i<a.length;i++){
        if(a[i]!==-1){
            a[i]=heights.pop();
        }
    }
    return a;
}
```

</details>

<br><br><br>

---
 
## 13. reverseInParentheses

Write a function that reverses characters in (possibly nested) parentheses in the input string.

Input strings will always be well-formed with matching `()`s.

### Example

- For `inputString = "(bar)"`, the output should be
`reverseInParentheses(inputString) = "rab"`;
- For `inputString = "foo(bar)baz"`, the output should be
`reverseInParentheses(inputString) = "foorabbaz"`;
- For `inputString = "foo(bar)baz(blim)"`, the output should be
`reverseInParentheses(inputString) = "foorabbazmilb"`;
- For `inputString = "foo(bar(baz))blim"`, the output should be
`reverseInParentheses(inputString) = "foobazrabblim"`.

    Because `"foo(bar(baz))blim"` becomes `"foo(barzab)blim"` and then `"foobazrabblim"`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] string inputString

    A string consisting of lowercase English letters and the characters `(` and `)`. It is guaranteed that all parentheses in `inputString` form a regular bracket sequence.

    _Guaranteed constraints:_

    `0 ≤ inputString.length ≤ 50`.

- [output] string

    Return `inputString`, with all the characters that were in parentheses reversed.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function reverseInParentheses(inputString) {
    const str=inputString
    if(str.match(/\([a-z]*\)/)){
        return reverseInParentheses(str.replace(/\([a-z]*\)/, 
            Array.from(str.match(/\([a-z]*\)/)[0].replace(/\(|\)/g,'')).reverse().join('')));
    }
    return str;
}
// had to look up the regex, and see some example code to figure it out using recursion.
```

</details>

<br><br><br>

--- 
