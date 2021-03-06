# Intro Gates <br><br><br>

---

## 1. addTwoDigits

You are given a two-digit integer `n`. Return the sum of its digits.

### Example

For `n = 29`, the output should be

`addTwoDigits(n) = 11`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer n

    A positive two-digit integer.

    _Guaranteed constraints:_

    `10 ≤ n ≤ 99`.

- [output] integer

    The sum of the first and second digits of the input number.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function addTwoDigits(n) {
    return Math.floor(n/10)+n%10;
}
//This works because the first number can never be 0 so flooring it will remove the decimal (leaving the tens place), and the remainder will be added to the floored number (including 0, as the second digit can be 0, just not the first).
```

</details>

<br><br><br>

--- 

## 2. largestNumber

Given an integer `n`, return the largest number that contains exactly `n` digits.

### Example

For `n = 2`, the output should be
`largestNumber(n) = 99`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer n

    _Guaranteed constraints:_
    `1 ≤ n ≤ 9.`

- [output] integer

    The largest integer of length n.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function largestNumber(n) {
    let num='';
    for(let i=0;i<n;i++){
        num+='9';
    }
    return parseInt(num);
}
//loop number of times and concat '9' for each iteration.  turn into int
```

</details>

<br><br><br>

--- 

## 3. candies

`n` children have got `m` pieces of candy. They want to eat as much candy as they can, but each child must eat exactly the same amount of candy as any other child. Determine how many pieces of candy will be eaten by all the children together. Individual pieces of candy cannot be split.

### Example

For `n = 3` and `m = 10`, the output should be
`candies(n, m) = 9`.

Each child will eat `3` pieces. So the answer is `9`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer n

    The number of children.

    _Guaranteed constraints:_
    
    `1 ≤ n ≤ 10`.

- [input] integer m

    The number of pieces of candy.

    _Guaranteed constraints:_

    `2 ≤ m ≤ 100`.

- [output] integer

    The total number of pieces of candy the children will eat provided they eat as much as they can and all children eat the same amount.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function candies(n, m) {
    return m-(m%n);
}
// in example n=3 (3 children) m=10 (10 pieces of candy) m % n = 10 % 9 = '1', so 10-1 = '9'
```

</details>

<br><br><br>

--- 

## 4. seatsInTheater

Your friend advised you to see a new performance in the most popular theater in the city. He knows a lot about art and his advice is usually good, but not this time: the performance turned out to be awfully dull. It's so bad you want to sneak out, which is quite simple, especially since the exit is located right behind your row to the left. All you need to do is climb over your seat and make your way to the exit.

The main problem is your shyness: you're afraid that you'll end up blocking the view (even if only for a couple of seconds) of all the people who sit behind you and in your column or the columns to your left. To gain some courage, you decide to calculate the number of such people and see if you can possibly make it to the exit without disturbing too many people.

Given the total number of rows and columns in the theater (`nRows` and `nCols`, respectively), and the `row` and `column` you're sitting in, return the number of people who sit strictly behind you **and** in your column or to the left, assuming all seats are occupied.

### Example

For `nCols = 16`, `nRows = 11`, `col = 5`, and `row = 3`, the output should be

`seatsInTheater(nCols, nRows, col, row) = 96`.

Here is what the theater looks like:

![Example image](https://github.com/SUBstylee/codeChallenges/blob/main/codeSignal/arcade/imgs/seatsInTheater.png?raw=true)

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer nCols

    An integer, the number of theater's columns.

    _Guaranteed constraints:_

    `1 ≤ nCols ≤ 1000`.

- [input] integer nRows

    An integer, the number of theater's rows.

    _Guaranteed constraints:_

    `1 ≤ nRows ≤ 1000`.

- [input] integer col

    An integer, the column number of your own seat (1-based).

    _Guaranteed constraints:_

    `1 ≤ col ≤ nCols`.

- [input] integer row

    An integer, the row number of your own seat (1-based).

    _Guaranteed constraints:_

    `1 ≤ row ≤ nRows`.

- [output] integer

    The number of people who sit strictly behind you and in your column or to the left.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function seatsInTheater(nCols, nRows, col, row) {
    return (nCols-col+1)*(nRows-row);
}
```

</details>

<br><br><br>

---
 
## 5. maxMultiple

Given a `divisor` and a `bound`, find the largest integer `N` such that:

`N` is divisible by `divisor`.
`N` is less than or equal to `bound`.
`N` is greater than `0`.
It is guaranteed that such a number exists.

### Example

For `divisor = 3` and `bound = 10`, the output should be

`maxMultiple(divisor, bound) = 9`.

The largest integer divisible by `3` and not larger than `10` is `9`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer divisor

    _Guaranteed constraints:_

    `2 ≤ divisor ≤ 10`.

- [input] integer bound

    _Guaranteed constraints:_

    `5 ≤ bound ≤ 100`.

- [output] integer

    The largest integer not greater than `bound` that is divisible by `divisor`.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function maxMultiple(divisor, bound) {
    // n=bound-(bound%divisor); //10-(10%3) = 10-1 = 9
    // console.log(n);
    return bound-(bound%divisor);
}

```

</details>

<br><br><br>

--- 

## 6. circleOfNumbers

Consider integer numbers from `0` to `n - 1` written down along the circle in such a way that the distance between any two neighboring numbers is equal (note that `0` and `n - 1` are neighboring, too).

Given `n` and `firstNumber`, find the number which is written in the radially opposite position to `firstNumber`.

### Example

For `n = 10` and `firstNumber = 2`, the output should be

`circleOfNumbers(n, firstNumber) = 7`.

![Example image](https://github.com/SUBstylee/codeChallenges/blob/main/codeSignal/arcade/imgs/circleOfNumbers.png?raw=true)

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer n

    A positive even integer.

    _Guaranteed constraints:_

    `4 ≤ n ≤ 20`.

- [input] integer firstNumber

    _Guaranteed constraints:_
    
    `0 ≤ firstNumber ≤ n - 1`.

- [output] integer

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function circleOfNumbers(n, firstNumber) {
    const oppNum=n/2+firstNumber //10/2+2 = 5+2 = 7
    // console.log(oppNum, oppNum>n-1?oppNum-n:oppNum); //changed if else statement to ternary operator
    return oppNum>n-1?oppNum-n:oppNum;
}
```

</details>

<br><br><br>

--- 

## 7. lateRide

One night you go for a ride on your motorcycle. At `00:00` you start your engine, and the built-in timer automatically begins counting the length of your ride, in minutes. Off you go to explore the neighborhood.

When you finally decide to head back, you realize there's a chance the bridges on your route home are up, leaving you stranded! Unfortunately, you don't have your watch on you and don't know what time it is. All you know thanks to the bike's timer is that `n` minutes have passed since `00:00`.

Using the bike's timer, calculate the current time. Return an answer as the sum of digits that the digital timer in the format `hh:mm` would show.

### Example

- For `n = 240`, the output should be

    `lateRide(n) = 4`.

    Since `240` minutes have passed, the current time is `04:00`. The digits sum up to `0 + 4 + 0 + 0 = 4`, which is the answer.

- For `n = 808`, the output should be

    `lateRide(n) = 14`.

    `808` minutes mean that it's `13:28` now, so the answer should be `1 + 3 + 2 + 8 = 14`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer n

    The duration of your ride, in minutes. It is guaranteed that you've been riding for less than a day (24 hours).

    _Guaranteed constraints:_

    `0 ≤ n < 60 · 24`.

- [output] integer

    The sum of the digits the digital timer would show.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function lateRide(n) {
    if(n<10) return n;
    const hours = Math.floor(n/60); //will count hours, then remove decimals, minutes from decimals will be calculated in minutes variable
    const minutes = n-hours*60;
    return `${hours}${minutes}`.split('').reduce((total, acc)=>parseInt(total)+parseInt(acc)) //will remove trailing zeros
}
```

</details>

<br><br><br>

--- 

## 8. phoneCall

Some phone usage rate may be described as follows:

- first minute of a call costs `min1` cents,

- each minute from the 2nd up to 10th (inclusive) costs `min2_10` cents

- each minute after 10th costs `min11` cents.

    You have `s` cents on your account before the call. What is the duration of the longest call (in minutes rounded down to the nearest integer) you can have?

### Example

For `min1 = 3`, `min2_10 = 1`, `min11 = 2`, and `s = 20`, the output should be

`phoneCall(min1, min2_10, min11, s) = 14`.

Here's why:

- the first minute costs `3` cents, which leaves you with `20 - 3 = 17` cents;

- the total cost of minutes `2` through `10` is `1 * 9 = 9`, so you can talk 9 more minutes and still have `17 - 9 = 8` cents;

- each next minute costs `2` cents, which means that you can talk `8 / 2 = 4` more minutes.

Thus, the longest call you can make is `1 + 9 + 4 = 14` minutes long.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer min1

    _Guaranteed constraints:_

    `1 ≤ min1 ≤ 10`.

- [input] integer min2_10

    _Guaranteed constraints:_

    `1 ≤ min2_10 ≤ 10`.

- [input] integer min11

    _Guaranteed constraints:_

    `1 ≤ min11 ≤ 10`.

- [input] integer s

    _Guaranteed constraints:_

    `2 ≤ s ≤ 500`.

- [output] integer

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function phoneCall(min1, min2_10, min11, s) {
    let minutes = 0;
    let cost = 0;
    while(cost<=s){
        minutes++;
        if(minutes == 1) cost+= min1;
        if(minutes >=2&&minutes <=10) cost+= min2_10;
        if(minutes >10) cost+=min11;
    }
    return minutes-1; //need to take away one, because using while loop
}
```

</details>

<br><br><br>

--- 

