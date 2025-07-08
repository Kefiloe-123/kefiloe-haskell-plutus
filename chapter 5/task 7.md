HC5T7: The $ Operator

```haskell
-- Using the $ operator
result :: Int
result = sum $ map (*2) $ filter (>3) [1..10]

-- Main function to print result
main :: IO ()
main = print result
```

---

### Explanation:

* The `$` operator is used to reduce parentheses.
* `sum $ map (*2) $ filter (>3) [1..10]` is equivalent to `sum (map (*2) (filter (>3) [1..10]))`.

---

### Output:

```
72
```
