HC6T2: Implement a recursive function to compute the nth Fibonacci number.

```haskell
-- Recursive Fibonacci function
fibonacci :: Integer -> Integer
fibonacci 0 = 0
fibonacci 1 = 1
fibonacci n
  | n > 1     = fibonacci (n - 1) + fibonacci (n - 2)
  | otherwise = error "Fibonacci is not defined for negative numbers"

-- Main function to test fibonacci
main :: IO ()
main = do
    print (fibonacci 0)   -- Output: 0
    print (fibonacci 1)   -- Output: 1
    print (fibonacci 5)   -- Output: 5
    print (fibonacci 10)  -- Output: 55
```

---

### Explanation:

* Base cases:

  * `fibonacci 0 = 0`
  * `fibonacci 1 = 1`
* Recursive case:

  * `fibonacci n = fibonacci (n-1) + fibonacci (n-2)` for `n > 1`
* Negative input triggers an error.

---

### Output:

```
0
1
5
55
```
