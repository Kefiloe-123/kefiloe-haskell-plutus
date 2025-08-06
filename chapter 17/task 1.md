HC17T1: Severity Data Type and Semigroup Instance

```haskell
-- main.hs

-- Import Semigroup class from Data.Semigroup
import Data.Semigroup

-- Define Severity data type with four levels
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord)

-- Implement Semigroup instance for Severity
-- The higher severity (max) overrides the lower one
instance Semigroup Severity where
    (<>) = max

-- Main function to demonstrate combining severities
main :: IO ()
main = do
    let sev1 = Low
        sev2 = High
        sev3 = Medium
        sev4 = Critical

    -- Combine severities using <>
    putStrLn $ "Low <> High = " ++ show (sev1 <> sev2)
    putStrLn $ "Medium <> Low = " ++ show (sev3 <> sev1)
    putStrLn $ "High <> Critical = " ++ show (sev2 <> sev4)
    putStrLn $ "Critical <> Medium = " ++ show (sev4 <> sev3)
```

---

### 💡 Explanation:

* `Severity` derives `Ord` so `max` can compare severities by their order (`Low < Medium < High < Critical`).
* The `Semigroup` instance uses `max` to pick the higher severity when combining.
* `main` shows examples of combining severities with `<>`.

---

### 🛠️ How to Run:

Save the code to `main.hs`, then run:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o severityApp
./severityApp
```

---
