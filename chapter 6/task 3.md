HC6T3: Implement a function to compute the sum of elements in a list using foldr.

```haskell
-- sumList sums the elements of a list using foldr
sumList :: Num a => [a] -> a
sumList = foldr (+) 0

main :: IO ()
main = do
  let nums = [10, 20, 30, 40]
  putStrLn $ "Sum of the list: " ++ show (sumList nums)
```

When you run this, the output will be:

```
Sum of the list: 100
```
