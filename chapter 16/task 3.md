HC16T3: Factorial

```haskell
-- main.hs

-- Define a function to calculate the factorial of a non-negative integer
factorial :: Integer -> Integer
factorial 0 = 1                          -- Base case: factorial of 0 is 1
factorial n = n * factorial (n - 1)      -- Recursive case

-- Main function to run and test the factorial function
main :: IO ()
main = do
    -- Define the number to calculate factorial of
    let number = 5

    -- Calculate the factorial
    let result = factorial number

    -- Print the result
    putStrLn ("The factorial of " ++ show number ++ " is " ++ show result)
```

---

### 💬 Explanation:

* `factorial 0 = 1` is the **base case**.
* `factorial n = n * factorial (n - 1)` is the **recursive case**.
* `main` demonstrates how to use the function with the number `5`.

---

### ▶️ How to Run:

Save the code in `main.hs`, then run using:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o factorialApp
./factorialApp
```
