# Time Complexity (Big O)

## What is Big O?

- Big O, also known as Big O notation, represents an algorithm's worst-case complexity. It uses algebraic terms to describe the complexity of an algorithm.
- Big O defines the runtime required to execute an algorithm by identifying how the performance of your algorithm will change as the input size grows. But it does not tell you how fast your algorithm's runtime is.
- Big O notation measures the efficiency and performance of your algorithm using time and space complexity

## Time Complexity Chart

![complexity](/Users/mohsenoid/Development/Personal/Android-Interview-Questions/images/complexity.png)

- **O(1)** - *Excellent/Best*
  - When your calculation is not dependent on the input size, it is a constant time complexity.
- **O(log n)** - *Good*
  - When the input size is reduced by half, maybe when iterating, handling recursion, or whatsoever, it is a logarithmic time complexity.
- **O(n)** - *Fair*
  - When you have a single loop within your algorithm, it is linear time complexity.
- **O(n log n)** - *Bad*
- **O(n^2)**, **O(2^n)**, and **O(n!)** - *Horrible/Worst*
  - **O(n^2)**: When you have nested loops within your algorithm, meaning a loop in a loop, it is quadratic time complexity
  - **O2^n**: When the growth rate doubles with each addition to the input, it is exponential time complexity.

### Constant Time: O(1)

When your algorithm is not dependent on the input size n, it is said to have a constant time complexity with order O(1). This means that the run time will always be the same regardless of the input size.

```kotlin
fun getFirstElement(array: Array<Int>): Int {
    return array[0]
}

fun main() {
    val score = arrayOf(12, 55, 67, 94, 22)
    println(getFirstElement(score)) // 12
}
```

### Logarithm Time: O(log n)

This is similar to linear time complexity, except that the runtime does not depend on the input size but rather on half the input size. When the input size decreases on each iteration or step, an algorithm is said to have logarithmic time complexity.

This method is the second best because your program runs for half the input size rather than the full size. After all, the input size decreases with each iteration.

A great example is binary search functions, which divide your sorted array based on the target value.

For example, suppose you use a binary search algorithm to find the index of a given element in an array:

```kotlin
fun binarySearch(array:Array<Int>, target:Int) :Int {
    var firstIndex = 0
    var lastIndex = array.size - 1
    while (firstIndex <= lastIndex) {
        val middleIndex = (firstIndex + lastIndex) / 2

        if (array[middleIndex] == target) {
            return middleIndex
        }

        if (array[middleIndex] > target) {
            lastIndex = middleIndex - 1
        } else {
            firstIndex = middleIndex + 1
        }
    }
    return -1
}

fun main() {
    val score = arrayOf(12, 22, 45, 67, 96)
    println(binarySearch(score, 96)) // 4
}
```

### Linear Time: O(n)

You get linear time complexity when the running time of an algorithm increases linearly with the size of the input. This means that when a function has an iteration that iterates over an input size of n, it is said to have a time complexity of order O(n).

For example, if an algorithm is to return the factorial of any inputted number. This means if you input 5 then you are to loop through and multiply 1 by 2 by 3 by 4 and by 5 and then output 120:

```kotlin
fun calcFactorial(n: Int): Int {
    var factorial = 1

    for(i in 2..n) {
        factorial *= i
    }
    return factorial
}

fun main() {
    println(calcFactorial(5)) // 120
}
```

### Quadratic Time: O(n^2)

When you perform nested iteration, meaning having a loop in a loop, the time complexity is quadratic, which is horrible.

A perfect way to explain this would be if you have an array with n items. The outer loop will run n times, and the inner loop will run n times for each iteration of the outer loop, which will give total n^2 prints. If the array has ten items, ten will print 100 times (10^2).

Here is an example by [Jared Nielsen](https://jarednielsen.com/big-o-quadratic-time-complexity/), where you compare each element in an array to output the index when two elements are similar:

```kotlin
fun matchElements(array: Array<String>): String {
    for (i in array.indices) {
        for (j in array.indices) {
            if (i != j && array[i] == array[j]) {
                return "Match found at $i and $j"
            }
        }
    }
    return "No matches found 😞"
}

fun main() {
    val fruit = arrayOf("🍓", "🍐", "🍊", "🍌", "🍍", "🍑", "🍎", "🍈", "🍊", "🍇")
    println(matchElements(fruit)) // "Match found at 2 and 8"
}
```

### Exponential Time: O(2^n)

You get exponential time complexity when the growth rate doubles with each addition to the input (n), often iterating through all subsets of the input elements. Any time an input unit increases by 1, the number of operations executed is doubled.

The recursive Fibonacci sequence is a good example. Assume you're given a number and want to find the *n*th element of the Fibonacci sequence.

The Fibonacci sequence is a mathematical sequence in which each number is the sum of the two preceding numbers, where 0 and 1 are the first two numbers. The third number in the sequence is 1, the fourth is 2, the fifth is 3, and so on... (0, 1, 1, 2, 3, 5, 8, 13, …).

This means that if you pass in 6, then the 6th element in the Fibonacci sequence would be 8:

```kotlin
fun recursiveFibonacci(n: Int): Int {
    return if (n < 2) {
        n
    } else {
        recursiveFibonacci(n - 1) + recursiveFibonacci(n - 2)
    }
}

fun main() {
    println(recursiveFibonacci(6)) // 8
}
```