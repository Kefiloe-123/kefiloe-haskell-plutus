HC20T1: safeDivide with Maybe Monad

```haskell
-- main.hs

-- safeDivide performs division of two Ints safely,
-- returning Nothing if divisor is zero, else Just the result
safeDivide :: Int -> Int -> Maybe Int
safeDivide _ 0 = Nothing
safeDivide x y = Just (x `div` y)

-- Main function to demonstrate safeDivide
main :: IO ()
main = do
  putStrLn "Dividing 10 by 2:"
  print $ safeDivide 10 2   -- Just 5

  putStrLn "Dividing 10 by 0:"
  print $ safeDivide 10 0   -- Nothing

  putStrLn "Dividing 7 by 3:"
  print $ safeDivide 7 3    -- Just 2
```

---

### 💡 Explanation:

* `safeDivide` checks if the divisor is zero.
* Returns `Nothing` if zero, otherwise returns `Just` quotient.
* Uses `Maybe` to safely handle division errors.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o safeDivideApp
./safeDivideApp
```

---
