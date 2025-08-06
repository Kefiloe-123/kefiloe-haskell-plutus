HC19T4: liftAndMultiply with liftA2

```haskell
-- main.hs

import Control.Applicative (liftA2)

-- liftAndMultiply lifts a binary function (Int -> Int -> Int)
-- using liftA2 to work with Applicative types like Maybe or List
liftAndMultiply :: Applicative f => (Int -> Int -> Int) -> f Int -> f Int -> f Int
liftAndMultiply = liftA2

-- Example multiplication function
multiply :: Int -> Int -> Int
multiply x y = x * y

-- Main function to demonstrate liftAndMultiply
main :: IO ()
main = do
  -- Using Maybe
  let maybeX = Just 3
      maybeY = Just 4
      maybeZ = Nothing :: Maybe Int

  putStrLn "Multiplying Just 3 and Just 4 using liftAndMultiply:"
  print $ liftAndMultiply multiply maybeX maybeY   -- Just 12

  putStrLn "Multiplying Just 3 and Nothing using liftAndMultiply:"
  print $ liftAndMultiply multiply maybeX maybeZ   -- Nothing

  -- Using List
  let listX = [1, 2]
      listY = [10, 20]

  putStrLn "Multiplying lists [1,2] and [10,20] using liftAndMultiply:"
  print $ liftAndMultiply multiply listX listY
  -- Result: [10,20,20,40] (all combinations)
```

---

### 💡 Explanation:

* `liftA2` lifts a binary function to work inside any `Applicative`.
* Works with `Maybe`, `[]`, or other `Applicative` types.
* The example multiplies values inside `Maybe` or lists.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o liftAndMultiplyApp
./liftAndMultiplyApp
```

---
