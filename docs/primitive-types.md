#Primitive Types

## Integers in Python

Unlike C which supports various types of integers, Python integers are represented by only one primitive data type `int`. 
Integers in Python are **signed integers** - meaning there is an implicit sign attached whether its specified or not.
Depending on the integers value, Python represents integers in 3 different ways. This implementation enables `int` to 
represent integers of any size, and the transition between the different implementations is handle under the hood.

**Interned integers** - integers between `-5` and `256` are pre-created in a global cache for optimization purposes. 

**Fixed-precision integers** - this is a **two's complement binary** representation using a fit number of bits. This is 
most often 64 bits.

**Arbitrary-precision integer** - a Bignum implementation that enables the representation of integers of arbitrary size, limited only by
the computer's available memory.

## Two's complement binary representation

This is a method of representing signed integers in binary.

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
