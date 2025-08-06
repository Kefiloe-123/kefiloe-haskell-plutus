HC20T7: findFirst with Either Monad

```haskell
-- main.hs

-- findFirst searches for the first element that satisfies a condition.
-- If found, it returns Right element.
-- If not found, it returns a Left with an error message.
findFirst :: (a -> Bool) -> [a] -> Either String a
findFirst _ [] = Left "Error: No matching element found."
findFirst pred (x:xs)
  | pred x    = Right x
  | otherwise = findFirst pred xs

-- Main function to test findFirst
main :: IO ()
main = do
  let list = [1, 3, 5, 8, 10]

  -- Test: find first even number
  let result1 = findFirst even list
  putStrLn "Finding first even number:"
  print result1   -- Output: Right 8

  -- Test: find first number greater than 100
  let result2 = findFirst (>100) list
  putStrLn "\nFinding first number greater than 100:"
  print result2   -- Output: Left "Error: No matching element found."
```

---

### 💡 Explanation:

* `Either String a` is used for error handling.

  * `Left "Error message"` indicates failure.
  * `Right a` contains the successful result.
* The predicate function `(a -> Bool)` is applied to each element.
* The search stops at the first matching element.

---

### 🛠️ How to Run

Save this file as `main.hs` and run it:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o findFirstApp
./findFirstApp
```

---
