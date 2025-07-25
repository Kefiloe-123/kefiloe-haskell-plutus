HC12T3: Factorial Function

```haskell
-- This program defines a function to compute the factorial of a positive integer.
-- It reads an integer from the user and prints the factorial result.

-- Factorial function using recursion
factorial :: Int -> Int
factorial 0 = 1
factorial n = n * factorial (n - 1)

-- Main function
main :: IO ()
main = do
    -- Prompt the user for input
    putStrLn "Enter a positive integer:"
    input <- getLine

    -- Convert the input to an integer
    let number = read input :: Int

    -- Compute and print the factorial
    if number < 0 then
        putStrLn "Factorial is not defined for negative numbers."
    else
        putStrLn ("The factorial is: " ++ show (factorial number))
```

---

### ✅ How to run this:

* **In any Haskell editor or online compiler** (e.g. [replit.com](https://replit.com), [mycompiler.io](https://www.mycompiler.io)):

  1. Paste the code.
  2. Click **Run**.

* **Locally using GHC**:

  ```bash
  ghc Main.hs
  ./Main
  ```

---

### 🧮 Example:

```
Enter a positive integer:
5
The factorial is: 120
```
