# Recursive Algorithms

## Factorial

```c
// Recursive function to calculate factorial
int factorial(int n) {
    // Base case: factorial of 0 is 1
    if (n == 0)
        return 1;
    // Recursive case: n! = n * (n-1)!
    else
        return n * factorial(n - 1);
}
```

## Fibonacci

```c
// Recursive function to calculate Fibonacci number
int fibonacci(int n) {
    // Base cases: Fibonacci of 0 is 0, Fibonacci of 1 is 1
    if (n == 0)
        return 0;
    else if (n == 1)
        return 1;
    // Recursive case: fib(n) = fib(n-1) + fib(n-2)
    else
        return fibonacci(n - 1) + fibonacci(n - 2);
}
```

## GCD

```c

// Recursive function to find GCD of two numbers
int gcd(int a, int b) {
    if (b == 0)
        return a; // GCD is found when one number becomes 0
    else
        return gcd(b, a % b); // Recursive call with smaller number
}
```

