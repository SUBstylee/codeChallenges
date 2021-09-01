# Corner of 0s and 1s <br><br><br>

---

## 17. killK-thBit

In order to stop the Mad Coder evil genius you need to decipher the encrypted message he sent to his minions. The message contains several numbers that, when typed into a supercomputer, will launch a missile into the sky blocking out the sun, and making all the people on Earth grumpy and sad.

You figured out that some numbers have a modified single digit in their binary representation. More specifically, in the given number `n` the `kth` bit from the right was initially set to `0`, but its current value might be different. It's now up to you to write a function that will change the `kth` bit of `n` back to `0`.

### Example

- For `n = 37` and `k = 3`, the output should be

    `killKthBit(n, k) = 33`.

    `37`<sub>`10`</sub>` = 100`<mark>`1`</mark>`01`<sub>`2`</sub>` ~> 100`<mark>`0`</mark>`01`<sub>`2`</sub>` = 33`<sub>`10`</sub>.

- For `n = 37` and `k = 4`, the output should be

    `killKthBit(n, k) = 37`.

    The `4th` bit is `0` already (looks like the Mad Coder forgot to encrypt this number), so the answer is still `37`.

### Input/Output

- [execution time limit] 4 seconds (js)

- [input] integer n

    _Guaranteed constraints:_

    `0 ≤ n ≤ 2`<sup>`31`</sup>` - 1`.

- [input] integer k

    The `1-`based index of the changed bit (counting from the right).

    _Guaranteed constraints:_

    `1 ≤ k ≤ 31`.

- [output] integer

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript
function killKthBit(n, k) {
  return n & ~(1 << (k-1));
}
```

</details>

<br><br><br>

--- 

## 18. arrayPacking

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

--- 

## 19. rangeBitCount

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

--- 

## 20. mirrorBits

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

---
 
## 21. second-RightmostZeroBit

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

--- 

## 22. swapAdjacentBits

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

--- 

## 23. differentRightmostBit

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

--- 

## 24. equalPairOfBits

### **SOLUTION**

<details>
  <summary>Hidden, click for solution.</summary>

```javascript

```

</details>

<br><br><br>

--- 

