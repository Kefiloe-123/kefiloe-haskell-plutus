HC6T4: Implement a function to compute the product of elements in a list using foldl.

```haskell
-- Function to compute the product of elements in a list using foldl
productFoldl :: Num a => [a] -> a
productFoldl = foldl (*) 1

-- Example main to test the function
main :: IO ()
main = do
  let nums = [1, 2, 3, 4, 5]
  putStrLn $ "Product of " ++ show nums ++ " is " ++ show (productFoldl nums)
```

### Explanation:

* `foldl (*) 1` folds the list from the left, starting with initial accumulator `1`.
* It multiplies each element by the accumulator, resulting in the product of all elements.

You can compile and run this code, and it will output:

```
Product of [1,2,3,4,5] is 120
```

