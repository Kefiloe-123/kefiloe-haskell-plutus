HC17T8: foldWithSemigroup Function

```haskell
-- main.hs

import Data.Semigroup
import Data.Monoid

-- | foldWithSemigroup combines a non-empty list of elements using their Semigroup instance
--   It uses foldr1 which requires the list to be non-empty.
foldWithSemigroup :: Semigroup a => [a] -> a
foldWithSemigroup = foldr1 (<>)

-- Main function to demonstrate foldWithSemigroup
main :: IO ()
main = do
    -- Example 1: Combining strings
    let strings = ["Hello, ", "world", "!"]
    putStrLn $ "Combined strings: " ++ foldWithSemigroup strings

    -- Example 2: Combining Sum Int
    let sums = [Sum 10, Sum 20, Sum 5]
    let total = foldWithSemigroup sums
    putStrLn $ "Combined Sum: " ++ show (getSum total)
```

---

### 💡 Explanation:

* `foldWithSemigroup` takes a list of any type with a `Semigroup` instance and combines them with `<>`.
* Uses `foldr1` which requires the list to be non-empty (otherwise runtime error).
* Demonstrates with lists of `String` (concatenation) and `Sum Int` (addition).

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o foldSemigroupApp
./foldSemigroupApp
```

---
