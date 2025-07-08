 HC6T1: Implement a recursive function to compute the factorial of a number.

```haskell
-- Recursive factorial function
factorial :: Integer -> Integer
factorial 0 = 1
factorial n
  | n > 0     = n * factorial (n - 1)
  | otherwise = error "Factorial is not defined for negative numbers"

-- Main function to test factorial
main :: IO ()
main = do
    print (factorial 0)   -- Output: 1
    print (factorial 5)   -- Output: 120
    print (factorial 10)  -- Output: 3628800
```

---

### Explanation:

* **Base case:** `factorial 0 = 1`
* **Recursive case:** `factorial n = n * factorial (n - 1)` for positive `n`.
* Handles negative input with an error message.

---

### Output:

```
1
120
3628800
```
