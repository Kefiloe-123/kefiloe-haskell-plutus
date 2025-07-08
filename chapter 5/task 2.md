HC5T2: Filtering Odd Numbers

```haskell
-- Extract odd numbers from 1 to 30 using filter
extractOdds :: [Int]
extractOdds = filter odd [1..30]

main :: IO ()
main = print extractOdds
```

---

### Explanation:

* `filter odd [1..30]` keeps only the elements of `[1..30]` for which `odd` returns `True`.
* `odd` is a built-in function that returns `True` for odd numbers.

---

### Output when you run main:

```
[1,3,5,7,9,11,13,15,17,19,21,23,25,27,29]
```
