HC16T6: nth Fibonacci Number

```haskell
-- main.hs

-- Define a function to compute the nth Fibonacci number using recursion
fibonacci :: Int -> Int
fibonacci 0 = 0                       -- Base case: fib(0) = 0
fibonacci 1 = 1                       -- Base case: fib(1) = 1
fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)
-- Recursive case: fib(n) = fib(n-1) + fib(n-2)

-- Main function to test the fibonacci function
main :: IO ()
main = do
    -- Define the position in the Fibonacci sequence
    let n = 10

    -- Calculate the nth Fibonacci number
    let result = fibonacci n

    -- Print the result
    putStrLn ("The " ++ show n ++ "th Fibonacci number is: " ++ show result)
```

---

### 🛠️ How to Run:

1. Save the code above in a file called `main.hs`.
2. Run it using:

```bash
runghc main.hs
```

Or compile it:

```bash
ghc main.hs -o fibonacciApp
./fibonacciApp
```

---
