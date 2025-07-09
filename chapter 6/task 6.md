HC6T6: Implement a function that determines whether a given element exists in a list.

```haskell
-- Recursive function to check if an element exists in a list
elementExists :: Eq a => a -> [a] -> Bool
elementExists _ [] = False
elementExists y (x:xs)
  | y == x    = True
  | otherwise = elementExists y xs

-- Example main to test the function
main :: IO ()
main = do
  let list = [1, 2, 3, 4, 5]
  print $ elementExists 3 list   -- Should print True
  print $ elementExists 6 list   -- Should print False
```

### Explanation:

* **Base case:** if the list is empty (`[]`), return `False`.
* **Recursive step:** if the head (`x`) equals the searched element (`y`), return `True`; otherwise, recursively check the tail (`xs`).

### Example output:

```
True
False
```
