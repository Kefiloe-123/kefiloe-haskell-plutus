HC5T9: Higher-Order Function to Transform a List

```haskell
-- Define transformList: applies function f twice to each element in the list
transformList :: (a -> a) -> [a] -> [a]
transformList f = map (f . f)

-- Example functions
increment :: Int -> Int
increment x = x + 1

square :: Int -> Int
square x = x * x

-- Main to test transformList
main :: IO ()
main = do
    print (transformList increment [1, 2, 3]) -- Output: [3,4,5] (increment twice)
    print (transformList square [1, 2, 3])    -- Output: [1,16,81] (square twice: x^4)
```

---

### Explanation:

* `transformList f` uses `map` to apply `(f . f)` (function composition) to each element.
* `(f . f) x = f (f x)` applies `f` twice.

---

### Output:

```
[3,4,5]
[1,16,81]
```
