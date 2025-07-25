HC12T4: First 10 Fibonacci Numbers

```haskell
-- This program defines a recursive function to compute Fibonacci numbers
-- and prints the first 10 Fibonacci numbers.

-- Recursive function to compute the nth Fibonacci number
fibonacci :: Int -> Int
fibonacci 0 = 0
fibonacci 1 = 1
fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)

-- Main function to compute and print the first 10 Fibonacci numbers
main :: IO ()
main = do
    putStrLn "The first 10 Fibonacci numbers are:"
    print [fibonacci n | n <- [0..9]]
```

---

### ✅ How to run:

* **In an online Haskell compiler** (e.g. [mycompiler.io](https://www.mycompiler.io)):

  1. Paste the code.
  2. Click **Run**.

* **On your local system using GHC**:

  ```bash
  ghc Main.hs
  ./Main
  ```

---

### 🧾 Example Output:

```
The first 10 Fibonacci numbers are:
[0,1,1,2,3,5,8,13,21,34]
```
