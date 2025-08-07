HC20T19: Writer Monad-based Logging System

```haskell
-- main.hs
-- Demonstrates logging function calls and arguments using the Writer monad

import Control.Monad.Writer

-- Define a type alias for logging with a list of strings
type Logger = Writer [String]

-- A sample function that adds two numbers and logs the call
add :: Int -> Int -> Logger Int
add x y = do
  tell ["Called add with arguments: " ++ show x ++ ", " ++ show y]
  return (x + y)

-- A sample function that multiplies two numbers and logs the call
multiply :: Int -> Int -> Logger Int
multiply x y = do
  tell ["Called multiply with arguments: " ++ show x ++ ", " ++ show y]
  return (x * y)

-- A function that uses add and multiply and logs all calls
calculate :: Int -> Int -> Logger Int
calculate x y = do
  sumResult <- add x y
  productResult <- multiply x y
  tell ["Sum is " ++ show sumResult ++ ", product is " ++ show productResult]
  return (sumResult + productResult)

-- Main function to run the logger and print output
main :: IO ()
main = do
  let (result, log) = runWriter (calculate 3 5)
  putStrLn $ "Final result: " ++ show result
  putStrLn "Log of function calls:"
  mapM_ putStrLn log
```

---

### 🧪 Example Output

```
Final result: 23
Log of function calls:
Called add with arguments: 3, 5
Called multiply with arguments: 3, 5
Sum is 8, product is 15
```

---

### Explanation

* We use the `Writer` monad to accumulate logs as a list of strings.
* Each function logs its name and arguments using `tell`.
* `calculate` calls both functions and logs the summary.
* `runWriter` unwraps the final value and the log.

---
