---
layout: post
title: Solving Fizz Buzz in Swift
---

Fizz Buzz is a classic engineering interview problem. Here's why you should know of it and be able to solve it. It's often used to quickly filter out candidates from the interview process and evaluate initial reasoning skills. All software engineers should know a solution to this problem.

### The problem
This is how to FizzBuzz problem will usually be presented:

>Write a program that prints the numbers from 1 to 100. But for multiples of three print "Fizz" instead of the number and for the multiples of five print "Buzz". For numbers which are multiples of both three and five print "FizzBuzz".

### Breaking down the problem using 'Divide and Conquer'
By reading the problem, we can deduce that there are four different cases to solve, three of which require the test: "Is `X` a multiple of `Y`".

#### Multiples Problem
3/4 cases require a solution to the problem: "Is `X` a multiple of `Y`".

This is solved using the modulo operator `%`.

```
If X modulo Y equals 0, then X is a multiple of Y.
```

#### Problems
1.  Print the `n` when it is __not a multiple of 3 *or* 5__.
2.  Print __"Fizz"__ when the `n` is a __multiple of 3 but not 5__.

    ```swift
    n % 3 == 0
    ```

3.  Print __"Buzz"__ when the `n` is a __multiple of 5 but not 3__

    ```swift
    n % 5 == 0
    ```
4.  Print __"FizzBuzz"__ when the `n` is a __multiple of both 5 *and* 3__

    ```swift
    n % 3 == 0 && n % 5 == 0
    ```

### Complete Solution 
By returning a `String` from the `FizzBuzz(:)` function, rather than printing from within, the function becomes testable.  

```swift
func FizzBuzz(i: Int) -> String {
    if i % 3 == 0 && i % 5 == 0 {
        return "FizzBuzz"
    } else if i % 3 == 0 {
        return "Fizz"
    } else if i % 5 == 0 {
        return "Buzz"
    } else {
       return "\(i)"
    }
}

for i in 1...100 {
    print(FizzBuzz(i))
} 
```

## Test cases
```swift
func testThatFactorsOfThreeOutputFizz() {
    XCTAssertEquals(FizzBuzz(3), "Fizz")
    XCTAssertEquals(FizzBuzz(6), "Fizz")
    XCTAssertEquals(FizzBuzz(9), "Fizz")
}

func testThatFactorsOfFiveOutputBuzz() {
    XCTAssertEquals(FizzBuzz(5), "Buzz")
    XCTAssertEquals(FizzBuzz(10), "Buzz")
    XCTAssertEquals(FizzBuzz(20), "Buzz")
}

func testThatFactorsOfFiveAndThreeOutputFizzBuzz() {
    XCTAssertEquals(FizzBuzz(15), "FizzBuzz")
    XCTAssertEquals(FizzBuzz(30), "FizzBuzz")
}

func testThatNumbersThatAreNotFactorsOfThreeOrFiveOutputThemselves() {
    XCTAssertEquals(FizzBuzz(1), "1")
    XCTAssertEquals(FizzBuzz(2), "2")
    XCTAssertEquals(FizzBuzz(7), "7")
}
```
