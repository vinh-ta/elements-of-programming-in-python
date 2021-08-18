#Primitive Types

## Integers in Python

Unlike C which supports various types of integers, Python integers are represented by only one primitive data type `int`. 
Integers in Python are **signed integers** - meaning there is an implicit sign attached whether its specified or not.
Depending on the integers value, Python represents integers in 3 different ways. This implementation enables `int` to 
represent integers of any size, and the transition between the different implementations is handled under the hood.

**Interned integers** - integers between `-5` and `256` are pre-created in a global cache for optimization purposes. 

**Fixed-precision integers** - this is a **two's complement binary** representation using a fit number of bits. This is 
most often 64 bits.

**Arbitrary-precision integer** - a Bignum implementation that enables the representation of integers of arbitrary size, limited only by
the computer's available memory.

## Two's complement binary representation

This is a method of representing signed integers in binary. To calculate the complement just requires a `NOT + 1`. The 
leading bit represents the sign with `0` being **positive** and `1` being **negative**.

```
Example for 0:

# 8 bits -> 0000000
# NOT -> 11111111
# +1 -> 00000000
```
The two's complement of zero is just `00000000`, so there is only one binary representation of zero in the **two's 
complement signed** system.

```
Example for 1, 2 & 3:
1: 00000001
-1: 11111111

2: 00000010
-2: 11111110

3: 00000011
-3: 11111101
```

This creates an asymmetrical distribution - with one more negative integer than positive integer. For an 8 bit signed 
integer, the range is between `-128` and `127`.


## Bitwise operators 

**Bitwise AND** - Returns `1` if both bits are `1` else `0`
```
x & y

Example:
# 6 & 4
# 0110 & 0100
# 0100

Answer: 4  
```
<br>

**Bitwise OR** - Returns `1` if either of the bits are `1` else `0`
```
x | y

Example:
# 1 | 2
# 0001 | 0010
# 0000

Answer: 0  
```
<br>

**Bitwise XOR** - Returns `1` if only one of the bits is `1` else `0`
```
x ^ y

Example:
# 5 ^ 6
# 0101 ^ 0110
# 0011

Answer: 3
```
<br>

**Bitwise NOT** - Returns `1` if `0` else `0`
```
~x

Example 1:
# ~0
# ~0000
# 1111

Answer: -1

Example 2:
# ~2
# ~0010
# 1101 
 
Answer: -3  
```
<br>

**Bitwise left shift** - Moves the bits to the left by a number places specified by the second
operand. The gaps are filled with `0` bits. A single shift is equivalent to multiplying by 2.
```
x << y

Example 1:
# 2 << 1
# 0010 << 1
# 00100

Answer: 4

Example 2:
# 3 << 2
# 0011 << 2
# 001100
 
Answer: 12 
```
<br>

**Bitmasked left shift** - Masking can be used to constraint the integer to a fixed number of bits by removing the 
required number of leading bits.

```
(x << y) & mask 

Example without masking:
# 39 << 3 
# 00100111 << 3
# 00100111000

Answer: 312

Example masking to 8 bits:
# (39 << 3) & 255 
# (00100111 << 3) & 11111111
# 00100111000 & 11111111
# 00111000

Answer: 56
```
<br>

**Bitwise right shift** - Moves the bits to the right by a number places specified by the second
operand. The rightmost bits are removed. The implicit sign is preserved when no more shifts can take place. 
A single shift divides the number by 2, ignoring any remainder.
```
x >> y

Example 1:
# 8 >> 1
# 1000 >> 2
# 0100

Answer: 4

Example 2:
# -16 >> 2
# 11110000 >> 2
# 111100
 
Answer: -4

Example 3:
# 5 >> 10
# 0101 >> 10
# 0

Answer: 0 

Example 4:
# -5 >> 10
# 1011 >> 10
# 1 

Answer: -1
```
<br>