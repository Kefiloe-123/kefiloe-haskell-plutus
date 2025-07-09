HC7T3: Implement a function using multiple constraints

```haskell
-- Function to compare two values and return the larger one
compareValues :: (Eq a, Ord a) => a -> a -> a
compareValues x y
  | x >= y    = x
  | otherwise = y

-- Example main to test the function
main :: IO ()
main = do
  putStrLn $ "Larger of 5 and 10 is: " ++ show (compareValues 5 10)
  putStrLn $ "Larger of 42 and 17 is: " ++ show (compareValues 42 17)
  putStrLn $ "Larger of 'a' and 'z' is: " ++ show (compareValues 'a' 'z')
```

---

### ✅ Example Output:

```
Larger of 5 and 10 is: 10
Larger of 42 and 17 is: 42
Larger of 'a' and 'z' is: 'z'
```

---

### ✔️ Explanation:

* The type signature `(Eq a, Ord a) => a -> a -> a` ensures that the type `a` supports both **equality comparison** (`==`) and **ordering** (`>=`, `<`).
* The function uses a simple guard:

  * If `x >= y`, return `x`.
  * Otherwise, return `y`.
