HC6T9: Implement a function that applies a given function to each element of a list (map implementation).

```haskell
-- Recursive implementation of map
myMap :: (a -> b) -> [a] -> [b]
myMap _ [] = []
myMap f (x:xs) = f x : myMap f xs

-- Example main to test the function
main :: IO ()
main = do
  let numbers = [1, 2, 3, 4, 5]
  let doubledNumbers = myMap (*2) numbers
  putStrLn $ "Original list: " ++ show numbers
  putStrLn $ "Doubled list: " ++ show doubledNumbers
```

### Explanation:

* **Base case:** if the list is empty, return an empty list.
* **Recursive step:** apply the function `f` to the head `x`, then recursively map over the tail `xs`.

### Example output:

```
Original list: [1,2,3,4,5]
Doubled list: [2,4,6,8,10]
```

✅ This code will compile and run correctly.

