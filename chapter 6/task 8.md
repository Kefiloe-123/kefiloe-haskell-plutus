HC6T8: Implement a function that filters all even numbers from a list.

```haskell
-- Recursive function to filter even numbers from a list
filterEvens :: [Int] -> [Int]
filterEvens [] = []
filterEvens (x:xs)
  | even x    = x : filterEvens xs
  | otherwise = filterEvens xs

-- Example main to test the function
main :: IO ()
main = do
  let numbers = [1, 2, 3, 4, 5, 6, 7, 8]
  putStrLn $ "Even numbers: " ++ show (filterEvens numbers)
```

### Explanation:

* **Base case:** an empty list returns an empty list.
* **Recursive step:** if the head `x` is even (`even x`), include it in the result and continue with the tail `xs`. Otherwise, skip it.

### Example output:

```
Even numbers: [2,4,6,8]
```

✅ This code will run correctly in a Haskell environment.

If you prefer a version using the built-in `filter` function, it would look like this:

```haskell
filterEvens = filter even
```
