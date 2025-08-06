HC19T3: safeProduct for Maybe Int


```haskell
-- main.hs

import Data.Maybe (fromMaybe)

-- safeProduct calculates the product of a list of Maybe Int values.
-- Returns Nothing if any element is Nothing, else the product of all values.
safeProduct :: [Maybe Int] -> Maybe Int
safeProduct = foldr multiply (Just 1)
  where
    multiply :: Maybe Int -> Maybe Int -> Maybe Int
    multiply (Just x) (Just y) = Just (x * y)
    multiply _ _               = Nothing

-- Main function to demonstrate safeProduct
main :: IO ()
main = do
  let list1 = [Just 2, Just 3, Just 4]
  let list2 = [Just 2, Nothing, Just 4]

  putStrLn "Product of [Just 2, Just 3, Just 4]:"
  print $ safeProduct list1  -- Just 24

  putStrLn "Product of [Just 2, Nothing, Just 4]:"
  print $ safeProduct list2  -- Nothing
```

---

### 💡 Explanation:

* `safeProduct` folds from the right, multiplying `Maybe Int` values.
* If any value is `Nothing`, the entire result is `Nothing`.
* Starts folding with `Just 1` (the identity for multiplication).

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o safeProductApp
./safeProductApp
```

---
