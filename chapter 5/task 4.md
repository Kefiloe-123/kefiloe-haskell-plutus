HC5T4: Using Lambda Functions

```haskell
-- Define biggerThan10 as a lambda function
biggerThan10 :: Int -> Bool
biggerThan10 = \x -> x > 10

-- Main function to test biggerThan10
main :: IO ()
main = do
    print (biggerThan10 5)    -- Output: False
    print (biggerThan10 15)   -- Output: True
```

---

### Explanation:

* Instead of defining `biggerThan10 x = x > 10`, we define it as `biggerThan10 = \x -> x > 10`.
* This means `biggerThan10` is a function that takes an argument `x` and returns `x > 10`.

---

### Output:

```
False
True
```
