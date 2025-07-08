HC6T5: Implement a function that reverses a list using recursion.

```haskell
-- Recursive function to reverse a list
reverseRecursive :: [a] -> [a]
reverseRecursive [] = []
reverseRecursive (x:xs) = reverseRecursive xs ++ [x]

-- Example main to test the function
main :: IO ()
main = do
  let list = [1, 2, 3, 4, 5]
  putStrLn $ "Original list: " ++ show list
  putStrLn $ "Reversed list: " ++ show (reverseRecursive list)
```

### Explanation:

* Base case: an empty list reversed is an empty list.
* Recursive step: reverse the tail `xs`, then append the head element `x` at the end.

When you run this, it will output:

```
Original list: [1,2,3,4,5]
Reversed list: [5,4,3,2,1]
```
