HC20T3: Writer Monad Logging Calculator

```haskell
-- main.hs

-- Import necessary modules
import Control.Monad.Writer

-- Define the type alias for our writer that logs String messages
type Calc a = Writer [String] a

-- Addition with logging
add :: Int -> Int -> Calc Int
add x y = do
  let result = x + y
  tell ["Added " ++ show x ++ " and " ++ show y ++ " to get " ++ show result]
  return result

-- Subtraction with logging
subtract' :: Int -> Int -> Calc Int
subtract' x y = do
  let result = x - y
  tell ["Subtracted " ++ show y ++ " from " ++ show x ++ " to get " ++ show result]
  return result

-- Multiplication with logging
multiply :: Int -> Int -> Calc Int
multiply x y = do
  let result = x * y
  tell ["Multiplied " ++ show x ++ " and " ++ show y ++ " to get " ++ show result]
  return result

-- Division with logging
divide :: Int -> Int -> Calc Int
divide _ 0 = do
  tell ["Attempted to divide by zero — Error!"]
  return 0  -- Return default value on error
divide x y = do
  let result = x `div` y
  tell ["Divided " ++ show x ++ " by " ++ show y ++ " to get " ++ show result]
  return result

-- Sample chained operations using do-notation
calculator :: Calc Int
calculator = do
  a <- add 5 3
  b <- multiply a 2
  c <- subtract' b 4
  d <- divide c 2
  return d

-- Main function to run the calculator and print result with logs
main :: IO ()
main = do
  let (result, logOutput) = runWriter calculator
  putStrLn $ "Final Result: " ++ show result
  putStrLn "Operations Log:"
  mapM_ putStrLn logOutput
```

---

### 🔎 What it does:

* Defines basic arithmetic functions using the `Writer` monad.
* Each function logs what it does.
* The `calculator` function chains operations and collects all logs.
* The `main` function runs it and prints the final result and the full log.

---

### 🛠️ How to run:

Save it as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o loggingCalc
./loggingCalc
```

---
