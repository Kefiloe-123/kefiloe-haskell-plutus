HC16T9: Remove Duplicates from List

```haskell
-- main.hs

-- Define a function to remove duplicates from a list
removeDuplicates :: (Eq a) => [a] -> [a]
removeDuplicates [] = []                                -- Base case: empty list
removeDuplicates (x:xs)
    | x `elem` xs = removeDuplicates xs                 -- If x is already in the rest, skip it
    | otherwise   = x : removeDuplicates xs            -- Otherwise, keep x

-- Main function to test removeDuplicates
main :: IO ()
main = do
    -- Define a list with duplicates
    let originalList = [1, 2, 3, 2, 4, 1, 5, 3]

    -- Remove duplicates using the function
    let uniqueList = removeDuplicates originalList

    -- Print the original and cleaned list
    putStrLn ("Original list: " ++ show originalList)
    putStrLn ("List without duplicates: " ++ show uniqueList)
```

---

### 🛠️ How to Run:

1. Save it as `main.hs`.
2. Then run with:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o removeDupApp
./removeDupApp
```

---
