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

Ratiorg got `statues` of different sizes as a present from CodeMaster for his birthday, each statue having an non-negative integer size. Since he likes to make things perfect, he wants to arrange them from smallest to largest so that each statue will be bigger than the previous one exactly by `1`. He may need some additional statues to be able to accomplish that. Help him figure out the minimum number of additional statues needed.

### Example

For `statues = [6, 2, 3, 8]`, the output should be
`makeArrayConsecutive2(statues) = 3`.

Ratiorg needs statues of sizes `4`, `5` and `7`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer statues

    An array of distinct non-negative integers.

    _Guaranteed constraints:_
    `1 ≤ statues.length ≤ 10`,
    `0 ≤ statues[i] ≤ 20`.

- [output] integer

    The minimal number of statues that need to be added to existing `statues` such that it contains every integer size from an interval `[L, R]` (for some `L, R`) and no other sizes.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function makeArrayConsecutive2(statues) {
    let numbers = statues;
    let count = 0;
    numbers.sort((a, b) => a - b);
    for(i=0;i<numbers.length-1;i++){
        if((numbers[i]-numbers[i+1])<-1){
            count+=Math.abs(numbers[i]-numbers[i+1])-1;
        }
    }    
    return count;
}
```

</details>

<br><br><br>

---

## 7. almostIncreasingSequence

Given a sequence of integers as an array, determine whether it is possible to obtain a strictly increasing sequence by removing no more than one element from the array.

_Note: sequence `a`<sub>`0`</sub>, `a`<sub>`1`</sub>, ..., `a`<sub>`n`</sub> is considered to be a strictly increasing if a0 < a1 < ... < an. Sequence containing only one element is also considered to be strictly increasing._

### Example

- For `sequence = [1, 3, 2, 1]`, the output should be
    `almostIncreasingSequence(sequence) = false`.

    <br>

    There is no one element in this array that can be removed in order to get a strictly increasing sequence.

<br>

- For `sequence = [1, 3, 2]`, the output should be
    `almostIncreasingSequence(sequence) = true`.

    <br>

    You can remove `3` from the array to get the strictly increasing sequence `[1, 2]`. Alternately, you can remove `2` to get the strictly increasing sequence `[1, 3]`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer sequence

    _Guaranteed constraints:_
    `2 ≤ sequence.length ≤ 10`<sup>`5`</sup>,
    `-10`<sup>`5`</sup>` ≤ sequence[i] ≤ 10`<sup>`5`</sup>.

- [output] boolean

    Return `true` if it is possible to remove one element from the array in order to get a strictly increasing sequence, otherwise return `false`.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function almostIncreasingSequence(sequence) {
    //console.log(sequence);
    let f = false;
    for (let i=0;i<sequence.length;i++) {
        if(sequence[i] <= sequence[i-1]) {
            if(f) {
                return false;
        }
        f = true;
        if(i === 1 || i + 1 === sequence.length) {
            continue;
        }
        else if (sequence[i] > sequence[i-2]) {
            sequence[i-1] = sequence[i-2];
        }
        else if(sequence[i-1] >= sequence[i+1]) {
            return false;
        }
        }
    }
    return true;
}

```

</details>

<br><br><br>

---

## 8 matrixElementsSum

After becoming famous, the CodeBots decided to move into a new building together. Each of the rooms has a different cost, and some of them are free, but there's a rumour that all the free rooms are haunted! Since the CodeBots are quite superstitious, they refuse to stay in any of the free rooms, or any of the rooms below any of the free rooms.

Given `matrix`, a rectangular matrix of integers, where each value represents the cost of the room, your task is to return the total sum of all rooms that are suitable for the CodeBots (ie: add up all the values that don't appear below a `0`).

### Example

For

```
matrix = [[0, 1, 1, 2], 
          [0, 5, 0, 0], 
          [2, 0, 3, 3]]
```

the output should be
`matrixElementsSum(matrix) = 9`.

![diagram for example 1](https://github.com/SUBstylee/codeChallenges/blob/main/codeSignal/arcade/imgs/matrixElementsSums1.png?raw=true)

There are several haunted rooms, so we'll disregard them as well as any rooms beneath them. Thus, the answer is `1 + 5 + 1 + 2 = 9`.

For

```
matrix = [[1, 1, 1, 0], 
          [0, 5, 0, 1], 
          [2, 1, 3, 10]]
```

the output should be
`matrixElementsSum(matrix) = 9`.

![diagram for example 2](https://github.com/SUBstylee/codeChallenges/blob/main/codeSignal/arcade/imgs/matrixElementsSums2.png?raw=true)

Note that the free room in the final column makes the full column unsuitable for bots (not just the room directly beneath it). Thus, the answer is `1 + 1 + 1 + 5 + 1 = 9`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.array.integer matrix

    <br>

    A 2-dimensional array of integers representing the cost of each room in the building. A value of `0` indicates that the room is haunted.

_Guaranteed constraints:_
`1 ≤ matrix.length ≤ 5`,
`1 ≤ matrix[i].length ≤ 5`,
`0 ≤ matrix[i][j] ≤ 10`.

- [output] integer
    <br>
    The total price of all the rooms that are suitable for the CodeBots to live in.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function matrixElementsSum(matrix) {
    console.log(matrix);
    let sum = 0;
    for(let i=0;i<matrix.length;i++){
        for(let j=0;j<matrix[i].length;j++){
            if(matrix[i][j]===0){
                for(let k=i+1;k<matrix.length;k++){
                    matrix[k][j]=0;
                }
            }
        }
    }
    for(let x=0;x<matrix.length;x++){
        for(let y=0;y<matrix[x].length;y++){
            sum+=matrix[x][y];
        }
    }
    return sum;
}
```

</details>

<br><br><br>

---
