# Tricks with bits

* x & (x-1) will clear the lowest set bit of x
* x & ~(x-1) extracts the lowest set bit of x (all others are clear). Pretty patterns when applied to a linear sequence.
* x & (x + (1 << n)) = x, with the run of set bits (possibly length 0) starting at bit n cleared.
* x & ~(x + (1 << n)) = the run of set bits (possibly length 0) in x, starting at bit n.
* x | (x + 1) = x with the lowest cleared bit set.
* x | ~(x + 1) = extracts the lowest cleared bit of x (all others are set).
* x | (x - (1 << n)) = x, with the run of cleared bits (possibly length 0) starting at bit n set.
* x | ~(x - (1 << n)) = the lowest run of cleared bits (possibly length 0) in x, starting at bit n are the only clear bits.

# Bitwise and logic operators

Now that you have learnt about bitwise operators, you must have realized & is very different from &&. Similarily | is very different from ||
& or | work on integers performing the operator on each corresponding bits. However, && or || work on boolean values ( Any non zero value is true ) to produce a boolean result.

Example :

   ```2  |   1  = 3
   2  ||  1  = true
   2   &  1  =  0
   2  &&  1  = true
   ```

Very similar to the fact that you can rewrite ```A = A + B as A += B```, you can rewrite 
```A = A | B as A |= B``` or
```A = A & B as A &= B```
