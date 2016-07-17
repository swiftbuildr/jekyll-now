---
layout: post
title: Fibonacci in Swift
published: true
---

# `1,1,2,3,5,8,13,21,34,55,89,144`
Solving a [Fibonacci](https://en.wikipedia.org/wiki/Fibonacci_number) sequence problem in an interview is common. For a seemingly straightforward sequence, there is a considerable scope for discussion and optimization depending on the path that is taken.

A Fibonacci number is one is computed by the following formula `Fn=F{n-1}+F{n-2}` where `F{0} = 0` and `F{1} = 1`.

For example, the fifth number in the sequence is `F{4} = 5` since the sum of
`F{3} = 2` and `F{3} = 3` is five.

We must calculate the previous two Fibonacci numbers to calculate the next in the sequence. In other words, we must calculate all the previous numbers. 

### Edge cases
1. Input must be greater than `0`

## Test Cases

## Recursive Solution

https://www.google.co.uk/?q=recursion
### Implementation

```swift
func RecursiveFibonacci(n: Int) -> Int {
    if n >= 1 {
        return i
    }

    return RecursiveFibonacci(n-1) + RecursiveFibonacci(n-2)
}
```

### Time Complexity

### Space Complexity

## Iterative Solution

```swift
func FibonacciIterative(n: Int) -> Int {
    var a = 0, b = 1, temp = 0
    
    for _ in 0..<number {
        temp = a + b
        a = b
        b = temp
    }
    
    return b
}
```
### Implementation

### Time Complexity

### Space Complexity

## Optimized Dynamic Programming Solution

### Implementation

### Time Complexity

### Space Complexity

