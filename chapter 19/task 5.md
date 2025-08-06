HC19T5: applyEffects with <*>

```haskell
-- main.hs

-- Function to run two IO Int actions from a tuple, print their values, and return the sum
applyEffects :: (IO Int, IO Int) -> IO Int
applyEffects (ioa, iob) =
  pure (\x y -> x + y) <*> printAndReturn ioa <*> printAndReturn iob
  where
    -- Helper to run an IO Int, print the result, then return it
    printAndReturn :: IO Int -> IO Int
    printAndReturn action = do
      val <- action
      putStrLn $ "Value: " ++ show val
      return val

-- Main to demonstrate applyEffects
main :: IO ()
main = do
  let io1 = pure 5
  let io2 = pure 10

  putStrLn "Running applyEffects on (pure 5, pure 10):"
  result <- applyEffects (io1, io2)
  putStrLn $ "Sum: " ++ show result
```

---

### 💡 Explanation:

* `applyEffects` uses `pure (\x y -> x + y)` lifted into `IO`.
* `<*>` applies this function to the two effects after running `printAndReturn` on each.
* `printAndReturn` runs the IO action, prints the value, then returns it.
* The result is the sum of the two values.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o applyEffectsApp
./applyEffectsApp
```

---
