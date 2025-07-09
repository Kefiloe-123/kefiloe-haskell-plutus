 HC6T7: Implement a function that takes a list and returns the length of the list.

```haskell
-- Recursive function to calculate the length of a list
listLength :: [a] -> Int
listLength [] = 0
listLength (_:xs) = 1 + listLength xs

-- Example main to test the function
main :: IO ()
main = do
  let list = [10, 20, 30, 40, 50]
  putStrLn $ "The length of the list is: " ++ show (listLength list)
```

### Explanation:

* **Base case:** an empty list `[]` has length `0`.
* **Recursive step:** for a non-empty list `(x:xs)`, count 1 for the head and add the length of the tail `xs`.

### Example output:

```
The length of the list is: 5
```

✅ This code will run correctly in a Haskell environment.
