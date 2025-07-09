 HC6T10: Implement a recursive function that takes a number and returns a list of its digits.

```haskell
-- Recursive function to split a number into its digits
digits :: Int -> [Int]
digits n
  | n < 10    = [n]
  | otherwise = digits (n `div` 10) ++ [n `mod` 10]

-- Example main to test the function
main :: IO ()
main = do
  let number = 12345
  putStrLn $ "Digits of " ++ show number ++ " are: " ++ show (digits number)
```

### Explanation:

* **Base case:** if the number is less than 10, return a list with the number itself.
* **Recursive step:** divide the number by 10 to remove the last digit and recursively extract the digits. Use `mod 10` to get the last digit and append it to the result.

### Example output:

```
Digits of 12345 are: [1,2,3,4,5]
```

---
