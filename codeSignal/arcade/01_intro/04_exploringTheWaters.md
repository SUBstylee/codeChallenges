# Exploring the Waters <br><br><br>

---

## 14. alternatingSums

Several people are standing in a row and need to be divided into two teams. The first person goes into team 1, the second goes into team 2, the third goes into team 1 again, the fourth into team 2, and so on.

You are given an array of positive integers - the weights of the people. Return an array of two integers, where the first element is the total weight of team 1, and the second element is the total weight of team 2 after the division is complete.

### Example

For `a = [50, 60, 60, 45, 70]`, the output should be
`alternatingSums(a) = [180, 105]`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer a

    _Guaranteed constraints:_

    `1 ≤ a.length ≤ 105`,

    `45 ≤ a[i] ≤ 100`.

- [output] array.integer

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function alternatingSums(a) {
    team1 = 0;
    team2 = 0;
    
    for(i =0;i<a.length;i++){
        if(i%2===0){
            team1+=a[i];
        }else{
            team2+=a[i];
        }
        
    }
    return [team1, team2];
}

```

</details>

<br><br><br>

--- 

## 15. addBorder

Given a rectangular matrix of characters, add a border of asterisks(*) to it.

### Example

For

```
picture = ["abc",
           "ded"]
```

the output should be

```
addBorder(picture) = ["*****",
                      "*abc*",
                      "*ded*",
                      "*****"]
```

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.string picture

    A non-empty array of non-empty equal-length strings.

    _Guaranteed constraints:_

    `1 ≤ picture.length ≤ 100`,
    
    `1 ≤ picture[i].length ≤ 100`.

- [output] array.string

    The same matrix of characters, framed with a border of asterisks of width `1`.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function addBorder(picture) {
    picture=picture.map(a=>'*'.concat(a,'*'));
    let tb=picture[0].length;
    picture.unshift(Array(tb).fill('*').join(''));
    picture.push(Array(tb).fill('*').join(''));
    return picture;
}
```

</details>

<br><br><br>

--- 

## 16. areSimilar

Two arrays are called similar if one can be obtained from another by swapping at most one pair of elements in one of the arrays.

Given two arrays `a` and `b`, check whether they are similar.

### Example

- For `a = [1, 2, 3]` and `b = [1, 2, 3]`, the output should be
`areSimilar(a, b) = true`.

    The arrays are equal, no need to swap any elements.

- For `a = [1, 2, 3]` and `b = [2, 1, 3]`, the output should be
`areSimilar(a, b) = true`.

    We can obtain b from a by swapping 2 and 1 in b.

- For `a = [1, 2, 2]` and `b = [2, 1, 1]`, the output should be
`areSimilar(a, b) = false`.

    Any swap of any two elements either in `a` or in `b` won't make `a` and `b` equal.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer a

    Array of integers.

    _Guaranteed constraints:_

    `3 ≤ a.length ≤ 105`,

    `1 ≤ a[i] ≤ 1000`.

- [input] array.integer b

    Array of integers of the same length as `a`.

    _Guaranteed constraints:_

    `b.length = a.length`,

    `1 ≤ b[i] ≤ 1000`.

- [output] boolean

    `true` if `a` and `b` are similar, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function areSimilar(a, b) {
    if(a.length !== b.length) return false;
    
    let d=[];
    for(let i=0;i<a.length;i++){
        if(a[i]!==b[i]){
            d.push(i)
            if(d.length>2) return false;
            if(d.length===2){
                if(a[d[0]]!==b[d[1]]||b[d[0]]!==a[d[1]]){
                    return false;
                }
            }
        }
    }
    return d.length===0||d.length==2;
}

```

</details>

<br><br><br>

--- 

## 17. arrayChange

You are given an array of integers. On each move you are allowed to increase exactly one of its element by one. Find the minimal number of moves required to obtain a strictly increasing sequence from the input.

### Example

For `inputArray = [1, 1, 1]`, the output should be
`arrayChange(inputArray) = 3`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer inputArray

    _Guaranteed constraints:_

    `3 ≤ inputArray.length ≤ 10`<sup>`5`</sup>,

    `-10`<sup>`5`</sup>` ≤ inputArray[i] ≤ 10`<sup>`5`</sup>.

- [output] integer

    The minimal number of moves needed to obtain a strictly increasing sequence from `inputArray`.
    
    It's guaranteed that for the given test cases the answer always fits signed `32`-bit integer type.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function arrayChange(inputArray) {
    let max=inputArray[0];
    let moves=0;
    for(let i=1;i<inputArray.length;i++){ //got stuck on this one, until I realized 'i' was initially set to '0' instead of '1' XD
        if(inputArray[i]<=max){
            moves+=max-inputArray[i]+1;
            inputArray[i]=max+1;
        }
        max=inputArray[i];
    }
    // console.log(moves);
    return moves;
}

```

</details>

<br><br><br>

---
 
## 18. palindromeRearranging

Given a string, find out if its characters can be rearranged to form a [palindrome](https://en.wikipedia.org/wiki/Palindrome).

### Example

For `inputString = "aabb"`, the output should be
`palindromeRearranging(inputString) = true`.

We can rearrange `"aabb"` to make `"abba"`, which is a palindrome.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] string inputString

    A string consisting of lowercase English letters.

    _Guaranteed constraints:_

    `1 ≤ inputString.length ≤ 50`.

- [output] boolean

    `true` if the characters of the `inputString` can be rearranged to form a palindrome, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function palindromeRearranging(inputString) {
    // O(2n) loops on every character, doubled because of spread **come back and see about not spreading**
    const strDict = [...inputString].reduce((acc,char)=>{ 
        acc[char] = acc[char]?acc[char]+1:1;
        return acc}, {});
    // O(m)
    const check = Object.values(strDict);
    let count = 0;
    // O(m)
    for(i=0;i<check.length;i++){
        if(check[i]%2!==0){
            count++
        }
    };
    return count<=1;
}

    // reduce big O to 'O(n)'
```

</details>

<br><br><br>

--- 
