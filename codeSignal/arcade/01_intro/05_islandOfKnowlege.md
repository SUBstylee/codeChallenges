# Island of Knowledge <br><br><br>

---

## 19. areEquallyStrong

Call two arms equally strong if the heaviest weights they each are able to lift are equal.

Call two people equally strong if their strongest arms are equally strong (the strongest arm can be both the right and the left), and so are their weakest arms.

Given your and your friend's arms' lifting capabilities find out if you two are equally strong.

### Example

- For `yourLeft = 10`, `yourRight = 15`, `friendsLeft = 15`, and `friendsRight = 10`, the output should be
`areEquallyStrong(yourLeft, yourRight, friendsLeft, friendsRight) = true`;
- For `yourLeft = 15`, `yourRight = 10`, `friendsLeft = 15`, and `friendsRight = 10`, the output should be
`areEquallyStrong(yourLeft, yourRight, friendsLeft, friendsRight) = true`;
- For `yourLeft = 15`, `yourRight = 10`, `friendsLeft = 15`, and `friendsRight = 9`, the output should be
`areEquallyStrong(yourLeft, yourRight, friendsLeft, friendsRight) = false`.
### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer yourLeft

    A non-negative integer representing the heaviest weight you can lift with your left arm.

    _Guaranteed constraints:_

    `0 ≤ yourLeft ≤ 20`.

- [input] integer yourRight

    A non-negative integer representing the heaviest weight you can lift with your right arm.

    _Guaranteed constraints:_

    `0 ≤ yourRight ≤ 20`.

- [input] integer friendsLeft

    A non-negative integer representing the heaviest weight your friend can lift with his or her left arm.

    _Guaranteed constraints:_

    `0 ≤ friendsLeft ≤ 20`.

- [input] integer friendsRight

    A non-negative integer representing the heaviest weight your friend can lift with his or her right arm.

    _Guaranteed constraints:_

    `0 ≤ friendsRight ≤ 20`.

- [output] boolean

    `true` if you and your friend are equally strong, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function areEquallyStrong(yourLeft, yourRight, friendsLeft, friendsRight) {
    return ((yourLeft+yourRight)===(friendsLeft+friendsRight))&&(yourLeft===friendsLeft||yourLeft===friendsRight||yourRight===friendsRight||yourRight===friendsLeft);
}
```

</details>

<br><br><br>

--- 

## 20. arrayMaximalAdjacentDifference

Given an array of integers, find the maximal absolute difference between any two of its adjacent elements.

### Example

For `inputArray = [2, 4, 1, 0]`, the output should be
`arrayMaximalAdjacentDifference(inputArray) = 3`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer inputArray

    _Guaranteed constraints:_

    `3 ≤ inputArray.length ≤ 10`,

    `-15 ≤ inputArray[i] ≤ 15`.

- [output] integer

    The maximal absolute difference.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function arrayMaximalAdjacentDifference(inputArray) {
    greatest = -Infinity;
    for(i=0;i<inputArray.length;i++){
        if(i!=inputArray.length){
            total=inputArray[i];
            total-=inputArray[i+1]
            if(Math.abs(total)>greatest){
            greatest=Math.abs(total);
            };
        };
        if(i!=0){
            total=inputArray[i]
            total-=inputArray[i-1]
            if(Math.abs(total)>greatest){
            greatest=Math.abs(total);
            };
        };
    };
    console.log(Math.abs(0))
    return greatest;
};

```

</details>

<br><br><br>

--- 

## 21. idIPv4Address

An IP address is a numerical label assigned to each device (e.g., computer, printer) participating in a computer network that uses the Internet Protocol for communication. There are two versions of the Internet protocol, and thus two versions of addresses. One of them is the [IPv4 address](https://en.wikipedia.org/wiki/IPv4).

Given a string, find out if it satisfies the IPv4 address naming rules.

### Example

- For `inputString = "172.16.254.1"`, the output should be
`isIPv4Address(inputString) = true`;

- For `inputString = "172.316.254.1"`, the output should be
`isIPv4Address(inputString) = false`.

    `316` is not in range `[0, 255]`.

- For `inputString = ".254.255.0"`, the output should be
`isIPv4Address(inputString) = false`.

    There is no first number.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] string inputString

    A string consisting of digits, full stops and lowercase English letters.

    _Guaranteed constraints:_

    `1 ≤ inputString.length ≤ 30`.

- [output] boolean

    `true` if `inputString` satisfies the IPv4 address naming rules, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function isIPv4Address(inputString) {
    let check = inputString.split('.');
    // check = check.filter((el)=>el!=null);
    console.log(check)
    if(check.length===4){
        for(i=0;i<4;i++){
            if(check[i]<0||check[i]>255||check[i]===''||check[i]==='00'||check[i]==='01'||isNaN(check[i])){
                return false;
            };
        };
        return true;
    } 
    return false;
}
//this one was tough.  had to look up 'isNaN()' as I have never encountered it before.
```

</details>

<br><br><br>

--- 

## 22. avoidObstacles

You are given an array of integers representing coordinates of obstacles situated on a straight line.

Assume that you are jumping from the point with coordinate `0` to the right. You are allowed only to make jumps of the same length represented by some integer.

Find the minimal length of the jump enough to avoid all the obstacles.

### Example

For `inputArray = [5, 3, 6, 7, 9]`, the output should be
`avoidObstacles(inputArray) = 4`.

Check out the image below for better understanding:

![Example image](https://github.com/SUBstylee/codeChallenges/blob/main/codeSignal/arcade/imgs/avoidObstacles.png?raw=true)

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] array.integer inputArray

    Non-empty array of positive integers.

    _Guaranteed constraints:_
    `2 ≤ inputArray.length ≤ 1000`,
`1 ≤ inputArray[i] ≤ 1000`.

- [output] integer

    The desired length.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function avoidObstacles(inputArray) {
    let jump=2;
    for(let i=0;i<inputArray.length;i++){
        if(inputArray[i]%jump===0){
            i=-1;
            jump++;
        }
    }
    return jump;
}
// O(n)
```

</details>

<br><br><br>

---
 
## ~~23. boxBlur~~

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

---
 
## ~~24. mineSweeper~~

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

--- 
