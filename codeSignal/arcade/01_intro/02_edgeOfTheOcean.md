# Edge of the Ocean <br><br><br>

## 4. adjacentElementsProduct

Given an array of integers, find the pair of adjacent elements that has the largest product and return that product.

### Example

For `inputArray = [3, 6, -2, -5, 7, 3]`, the output should be
`adjacentElementsProduct(inputArray) = 21`.

`7` and `3` produce the largest product.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer inputArray

    An array of integers containing at least two elements.

    _Guaranteed constraints:_
  
    `2 ≤ inputArray.length ≤ 10`,

    `-1000 ≤ inputArray[i] ≤ 1000`.

- [output] integer

    The largest product of adjacent elements.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function adjacentElementsProduct(inputArray) {
    let max = -Infinity;
    for (let i=1;i<inputArray.length;i++){
        max=Math.max(inputArray[i]*inputArray[i-1],max);
    }
    return max;
}
```

</details>

<br><br><br>

---

## 5. shapeArea

Below we will define an `n`-interesting polygon. Your task is to find the area of a polygon for a given `n`.

A `1`-interesting polygon is just a square with a side of length `1`. An `n`-interesting polygon is obtained by taking the `n - 1`-interesting polygon and appending `1`-interesting polygons to its rim, side by side. You can see the `1`-, `2`-, `3`- and `4`-interesting polygons in the picture below.

![diagram for shape area](https://github.com/SUBstylee/codeChallenges/blob/main/codeSignal/arcade/imgs/shapeArea.png?raw=true)

### Example

 - For `n = 2`, the output should be

    `shapeArea(n) = 5`;

 - For `n = 3`, the output should be

    `shapeArea(n) = 13`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer n

    _Guaranteed constraints:_
    `1 ≤ n < 10^4.`

- [output] integer

    The area of the `n`-interesting polygon.


### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function shapeArea(n) {
    return (n**2+(n-1)**2);
}
```

</details>

<br><br><br>

---

## 6. makeArrayConsecutive2

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

---

## 7. almostIncreasingSequence

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

---

## 8 matrixElementsSum

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

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

    -1000 ≤ param1 ≤ 1000.

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