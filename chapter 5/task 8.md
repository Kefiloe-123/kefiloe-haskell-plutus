HC5T8: Point-Free Style

```haskell
-- Point-free style definition of addFive
addFive :: Num a => a -> a
addFive = (+ 5)

-- Main function to test addFive
main :: IO ()
main = do
    print (addFive 10)  -- Output: 15
    print (addFive 0)   -- Output: 5
```

---

### Explanation:

* Instead of explicitly mentioning `x`, we directly use the partially applied `(+)` operator.
* `(+) 5` is a function that adds 5 to its argument.

---

### Output:

```
15
5
```
