# ~~At the Crossroads~~ <br><br><br>

---

## 9. reachNextLevel

You are playing an RPG game. Currently your experience points (XP) total is equal to `experience`. To reach the next level your XP should be at least at `threshold`. If you kill the monster in front of you, you will gain more experience points in the amount of the `reward`.

Given values `experience`, `threshold` and `reward`, check if you reach the next level after killing the monster.

### Example

- For `experience = 10`, `threshold = 15`, and `reward = 5`, the output should be

    `reachNextLevel(experience, threshold, reward) = true`;

- For `experience = 10`, `threshold = 15`, and `reward = 4`, the output should be

    `reachNextLevel(experience, threshold, reward) = false`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer experience

    _Guaranteed constraints:_

    `3 ≤ experience ≤ 250`.

- [input] integer threshold

    _Guaranteed constraints:_

    `5 ≤ threshold ≤ 300`.

- [input] integer reward

    _Guaranteed constraints:_

    `2 ≤ reward ≤ 65`.

- [output] boolean

    `true` if you reach the next level, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function reachNextLevel(experience, threshold, reward) {
    return experience+reward>=threshold?true:false;
}
```

</details>

<br><br><br>

--- 

## 10. knapsackLight

You found two items in a treasure chest! The first item weighs `weight1` and is worth `value1`, and the second item weighs `weight2` and is worth `value2`. What is the total maximum value of the items you can take with you, assuming that your max weight capacity is `maxW` and you can't come back for the items later?

Note that there are only two items and you can't bring more than one item of each type, i.e. you can't take two first items or two second items.

### Example

- For `value1 = 10`, `weight1 = 5`, `value2 = 6`, `weight2 = 4`, and `maxW = 8`, the output should be

    `knapsackLight(value1, weight1, value2, weight2, maxW) = 10`.

    You can only carry the first item.

- For `value1 = 10`, `weight1 = 5`, `value2 = 6`, `weight2 = 4`, and `maxW = 9`, the output should be

    `knapsackLight(value1, weight1, value2, weight2, maxW) = 16`.

    You're strong enough to take both of the items with you.

- For `value1 = 5`, `weight1 = 3`, `value2 = 7`, `weight2 = 4`, and `maxW = 6`, the output should be

    `knapsackLight(value1, weight1, value2, weight2, maxW) = 7`.

    You can't take both items, but you can take any of them.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer value1

    _Guaranteed constraints:_

    `2 ≤ value1 ≤ 20`.

- [input] integer weight1

    _Guaranteed constraints:_

    `2 ≤ weight1 ≤ 10`.

- [input] integer value2

    _Guaranteed constraints:_

    `2 ≤ value2 ≤ 20`.

- [input] integer weight2

    _Guaranteed constraints:_

    `2 ≤ weight2 ≤ 10`.

- [input] integer maxW

    _Guaranteed constraints:_

    `1 ≤ maxW ≤ 20`.

- [output] integer

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function knapsackLight(value1, weight1, value2, weight2, maxW) {
    let total = 0;
    if(maxW >= (weight1+weight2)){
        total = value1+value2;
    }else if(maxW >= weight1 && maxW >= weight2){
        total =  Math.max(value1, value2);
    }else if(maxW >= weight1 || maxW >= weight2){
        weight1<weight2?total=value1:total=value2;
    };
    return total;
}
```

</details>

<br><br><br>

--- 

## 11. extraNumber

You're given three integers, `a`, `b` and `c`. It is guaranteed that two of these integers are equal to each other. What is the value of the third integer?

### Example

For `a = 2`, `b = 7`, and `c = 2`, the output should be

`extraNumber(a, b, c) = 7`.

The two equal numbers are `a` and `c`. The third number (`b`) equals `7`, which is the answer.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer a

    _Guaranteed constraints:_

    `1 ≤ a ≤ 10`<sup>`9`</sup>.

- [input] integer b

    _Guaranteed constraints:_

    `1 ≤ b ≤ 10`<sup>`9`</sup>.

- [input] integer c

    _Guaranteed constraints:_

    `1 ≤ c ≤ 10`<sup>`9`</sup>.

- [output] integer

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function extraNumber(a, b, c) {
    if(a===b){
        return c;
    }
    return b===c?a:b;
}
```

</details>

<br><br><br>

--- 

## 12. isInfiniteProcess

Given integers `a` and `b`, determine whether the following pseudocode results in an infinite loop

```
while a is not equal to b do
  increase a by 1
  decrease b by 1
```

Assume that the program is executed on a virtual machine which can store arbitrary long numbers and execute forever.

### Example

- For `a = 2` and `b = 6`, the output should be

    `isInfiniteProcess(a, b) = false`;

- For `a = 2` and `b = 3`, the output should be

    `isInfiniteProcess(a, b) = true`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer a

    _Guaranteed constraints:_

    `0 ≤ a ≤ 20`.

- [input] integer b

    _Guaranteed constraints:_

    `0 ≤ b ≤ 20`.

- [output] boolean

    `true` if the pseudocode will never stop, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function isInfiniteProcess(a, b) {
    return a>b||a+1===b||(a%2!==0&&b%2===0)||(a%2===0&&b%2!==0);
    
}
```

</details>

<br><br><br>

---
 
## 13. arithmeticExpression

Consider an arithmetic expression of the form `a#b=c`. Check whether it is possible to replace `#` with one of the four signs: `+`, `-`, `*` or `/` to obtain a correct expression.

### Example

- For `a = 2`, `b = 3`, and `c = 5`, the output should be
    
    `arithmeticExpression(a, b, c) = true`.

    We can replace `#` with a `+` to obtain `2 + 3 = 5`, so the answer is `true`.

- For `a = 8`, `b = 2`, and `c = 4`, the output should be

    `arithmeticExpression(a, b, c) = true`.

- We can replace `#` with a `/` to obtain `8 / 2 = 4`, so the answer is `true`.

    For `a = 8`, `b = 3`, and `c = 2`, the output should be

    `arithmeticExpression(a, b, c) = false`.

    - `8 + 3 = 11 ≠ 2`;

    - `8 - 3 = 5 ≠ 2`;

    - `8 * 3 = 24 ≠ 2`;

    - `8 / 3 = 2.(6) ≠ 2`.

    So the answer is `false`.

### Input/Output

[execution time limit] 4 seconds (js)

- [input] integer a

    _Guaranteed constraints:_

    `1 ≤ a ≤ 20`.

- [input] integer b

    _Guaranteed constraints:_

    `1 ≤ b ≤ 20`.

- [input] integer c

    _Guaranteed constraints:_

    `0 ≤ c ≤ 20`.

- [output] boolean

    `true` if the desired replacement is possible, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function arithmeticExpression(a, b, c) {
    return a+b===c||a-b===c||a*b===c||a/b===c;
}
```

</details>

<br><br><br>

--- 

## 14. tennisSet

In tennis, the winner of a set is based on how many games each player wins. The first player to win `6` games is declared the winner unless their opponent had already won `5` games, in which case the set continues until one of the players has won `7` games.

Given two integers `score1` and `score2`, your task is to determine if it is possible for a tennis set to be finished with a final score of `score1` : `score2`.

### Example

- For `score1 = 3` and `score2 = 6`, the output should be

    `tennisSet(score1, score2) = true`.

    Since player 1 hadn't reached `5` wins, the set ends once player 2 has won `6` games.

- For `score1 = 8` and `score2 = 5`, the output should be

    `tennisSet(score1, score2) = false`.

    Since both players won at least `5` games, the set would've ended once one of them won the `7th` one.

- For `score1 = 6` and `score2 = 5`, the output should be

    `tennisSet(score1, score2) = false`.

    This set will continue until one of these players wins their `7th` game, so this can't be the final score.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer score1

    Number of games won by the `1st` player, non-negative integer.

    _Guaranteed constraints:_

    `0 ≤ score1 ≤ 10`.

- [input] integer score2

    Number of games won by the `2nd` player, non-negative integer.

    _Guaranteed constraints:_

    `0 ≤ score2 ≤ 10`.

- [output] boolean

    `true` if `score1 : score2` represents a possible score for an ended set, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function tennisSet(score1, score2) {
    return ((score1===6||score2===6)&&(score1<5||score2<5))||((score1===7||score2===7)&&(score1===5||score2===5||score1===6||score2===6));
}
```

</details>

<br><br><br>

--- 

## 15. willYou?

Once Mary heard a famous song, and a line from it stuck in her head. That line was "Will you still love me when I'm no longer young and beautiful?". Mary believes that a person is loved if and only if he/she is both young and beautiful, but this is quite a depressing thought, so she wants to put her belief to the test.

Knowing whether a person is `young`, `beautiful` and `loved`, find out if they contradict Mary's belief.

A person contradicts Mary's belief if one of the following statements is true:

- they are `young` and `beautiful` but not `loved`;

- they are `loved` but not `young` or not `beautiful`.

### Example

- For `young = true`, `beautiful = true`, and `loved = true`, the output should be

    `willYou(young, beautiful, loved) = false`.

    Young and beautiful people are loved according to Mary's belief.

- For `young = true`, `beautiful = false`, and `loved = true`, the output should be

    `willYou(young, beautiful, loved) = true`.

    Mary doesn't believe that not beautiful people can be loved.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] boolean young

- [input] boolean beautiful

- [input] boolean loved

- [output] boolean

    `true` if the person contradicts Mary's belief, `false` otherwise.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function willYou(young, beautiful, loved) {
    return ((!young||!beautiful)&&loved)||(young&&beautiful&&!loved);
}
```

</details>

<br><br><br>

--- 

## 16. metroCard

You just bought a public transit card that allows you to ride the Metro for a certain number of days.

Here is how it works: upon first receiving the card, the system allocates you a `31`-day pass, which equals the number of days in January. The second time you pay for the card, your pass is extended by `28` days, i.e. the number of days in February (note that leap years are not considered), and so on. The `13th` time you extend the pass, you get `31` days again.

You just ran out of days on the card, and unfortunately you've forgotten how many times your pass has been extended so far. However, you do remember the number of days you were able to ride the Metro during this most recent month. Figure out the number of days by which your pass will now be extended, and return all the options as an array sorted in increasing order.

### Example

For `lastNumberOfDays = 30`, the output should be

`metroCard(lastNumberOfDays) = [31]`.

There are `30` days in April, June, September and November, so the next months to consider are May, July, October or December. All of them have exactly `31` days, which means that you will definitely get a `31`-days pass the next time you extend your card.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer lastNumberOfDays

    A positive integer, the number of days for which the card was extended the last time.

    Guaranteed constraints:

    `lastNumberOfDays = 28 or lastNumberOfDays = 30 or lastNumberOfDays = 31`.

- [output] array.integer

    An array of positive integers, the possible number of days for which you will extend your pass. The elements of the array can only be equal to `28`, `30` or `31` and must be sorted in increasing order.

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function metroCard(lastNumberOfDays) {
    return lastNumberOfDays===31?[28,30,31]:[31];
}
```

</details>

<br><br><br>

--- 

