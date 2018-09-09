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

   ```
   2  |   1  = 3
   2  ||  1  = true
   2   &  1  =  0
   2  &&  1  = true
   ```

Very similar to the fact that you can rewrite ```A = A + B as A += B```, you can rewrite 
```A = A | B as A |= B``` or
```A = A & B as A &= B```

# Bit mask
Let say we design an object with 8 boolean properties. Instead of declaring 8 boolean variables, we can use a bit array to store 8 boolean properties. 

```
For example
short object_property_bit_array = 0;
```
Set each of boolean property as below
```
object_property_bit_array |= (1 << 0) --> set boolean property at index 0 is true.
object_property_bit_array |= (1 << 1) --> set boolean property at index 1 is true.
object_property_bit_array |= (1 << 2)
object_property_bit_array |= (1 << 3)
object_property_bit_array |= (1 << 4)
object_property_bit_array |= (1 << 5)
object_property_bit_array |= (1 << 6)
object_property_bit_array |= (1 << 7)
```

Such (1 << 0), ... (1 << 7) is called bit mask. 

To check the boolean property at index 6th is set
```if (object_property_bit_array & (1 << 6)) {
std::cout << "6th boolean property is true" << std::endl;
}
```
