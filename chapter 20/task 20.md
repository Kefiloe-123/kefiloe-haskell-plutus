HC20T20: batchProcessing with Monadic Bind

```haskell
-- main.hs
-- Demonstrates chaining multiple monadic actions using >>= (bind)

-- A simple monadic action: doubling a number and printing the result
doublePrint :: Int -> IO Int
doublePrint x = do
  let result = x * 2
  putStrLn $ "Doubled " ++ show x ++ " to get " ++ show result
  return result

-- Another monadic action: adding 3 and printing the result
addThreePrint :: Int -> IO Int
addThreePrint x = do
  let result = x + 3
  putStrLn $ "Added 3 to " ++ show x ++ " to get " ++ show result
  return result

-- batchProcessing chains the monadic actions using >>= (bind)
batchProcessing :: Int -> IO Int
batchProcessing x =
  doublePrint x >>= addThreePrint >>= doublePrint

-- Main function to run batchProcessing
main :: IO ()
main = do
  putStrLn "Starting batch processing with input 5:"
  finalResult <- batchProcessing 5
  putStrLn $ "Final result: " ++ show finalResult
```

---

### 🧪 Example Output

```
Starting batch processing with input 5:
Doubled 5 to get 10
Added 3 to 10 to get 13
Doubled 13 to get 26
Final result: 26
```

---

### Explanation

* `batchProcessing` chains three monadic actions (`doublePrint`, `addThreePrint`, then `doublePrint` again) using `(>>=)`.
* Each action receives the result of the previous one and returns a new `IO Int`.
* The final result is printed in `main`.

---
