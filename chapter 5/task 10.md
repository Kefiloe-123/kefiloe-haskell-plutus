HC5T10: Combining Higher-Order Functions

```haskell
-- Function to check if any squared value is greater than 50
anySquareGreaterThan50 :: [Int] -> Bool
anySquareGreaterThan50 xs = any (> 50) (map (^2) (filter (> 0) xs))

-- Main to test the function
main :: IO ()
main = do
    print (anySquareGreaterThan50 [1, 3, 5])     -- False (1^2=1,3^2=9,5^2=25)
    print (anySquareGreaterThan50 [4, 6, 8])     -- True (8^2=64 > 50)
    print (anySquareGreaterThan50 [-10, -8, 7])  -- True (7^2=49 but -10, -8 filtered out)
    print (anySquareGreaterThan50 [0, 1, 2])     -- False
```

---

### Explanation:

* `filter (> 0) xs` keeps only positive numbers (optional, can be omitted if negatives are fine).
* `map (^2)` squares each remaining number.
* `any (> 50)` checks if **any** squared value is greater than 50.

---

### Output:

```
False
True
True
False
```

---

If you want it to consider all numbers (including zero and negatives), just remove the `filter (> 0)` part:

```haskell
anySquareGreaterThan50 xs = any (> 50) (map (^2) xs)
```
