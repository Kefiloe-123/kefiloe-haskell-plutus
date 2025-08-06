HC19T2: addThreeApplicative Function

```haskell
-- main.hs

-- addThreeApplicative adds three Maybe Int values using Applicative style
addThreeApplicative :: Maybe Int -> Maybe Int -> Maybe Int -> Maybe Int
addThreeApplicative mx my mz =
  pure (\x y z -> x + y + z) <*> mx <*> my <*> mz
-- The function (\x y z -> x + y + z) is lifted into Maybe context and applied to the three Maybes

-- Main function to demonstrate addThreeApplicative
main :: IO ()
main = do
  let a = Just 10
      b = Just 20
      c = Just 30
      d = Nothing

  putStrLn "Adding Just 10, Just 20, Just 30:"
  print $ addThreeApplicative a b c  -- Should print Just 60

  putStrLn "Adding Just 10, Nothing, Just 30:"
  print $ addThreeApplicative a d c  -- Should print Nothing
```

---

### 💡 Explanation:

* Uses applicative style to add three `Maybe Int` values.
* If any input is `Nothing`, the result is `Nothing`.
* Otherwise, sums the contained values.

---

### 🛠️ How to Run:

Save the code as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o addThreeApp
./addThreeApp
```

---
