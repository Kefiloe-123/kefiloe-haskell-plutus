HC20T2: sequenceMaybe for List of Maybe

```haskell
-- main.hs

-- sequenceMaybe converts [Maybe a] to Maybe [a]
-- Returns Nothing if any element is Nothing
sequenceMaybe :: [Maybe a] -> Maybe [a]
sequenceMaybe [] = Just []
sequenceMaybe (x:xs) = do
  val <- x
  rest <- sequenceMaybe xs
  return (val : rest)

-- Main function to demonstrate sequenceMaybe
main :: IO ()
main = do
  let list1 = [Just 1, Just 2, Just 3]
  let list2 = [Just 1, Nothing, Just 3]

  putStrLn "Sequencing [Just 1, Just 2, Just 3]:"
  print $ sequenceMaybe list1  -- Just [1,2,3]

  putStrLn "Sequencing [Just 1, Nothing, Just 3]:"
  print $ sequenceMaybe list2  -- Nothing
```

---

### 💡 Explanation:

* `sequenceMaybe` recursively unwraps each `Maybe` in the list.
* Uses `do` notation to fail early if any element is `Nothing`.
* Returns `Just` list if all succeed, otherwise `Nothing`.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o sequenceMaybeApp
./sequenceMaybeApp
```

---
