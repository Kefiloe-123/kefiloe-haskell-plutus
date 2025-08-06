HC17T6: maxSeverity Function

```haskell
-- main.hs

import Data.Semigroup
import Data.Monoid

-- Define Severity data type
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord)

-- Semigroup instance: combine by taking the max (higher severity wins)
instance Semigroup Severity where
    (<>) = max

-- Monoid instance: identity is Low (lowest severity)
instance Monoid Severity where
    mempty = Low
    mappend = (<>)

-- Function to combine a list of Severity values using mconcat
maxSeverity :: [Severity] -> Severity
maxSeverity = mconcat
-- mconcat folds the list using the Monoid instance

-- Main function to test maxSeverity
main :: IO ()
main = do
    let severities = [Low, Medium, High, Medium, Critical, Low]

    putStrLn $ "List of severities: " ++ show severities
    putStrLn $ "Maximum severity: " ++ show (maxSeverity severities)
```

---

### 💡 Explanation:

* `Severity` has a `Semigroup` and `Monoid` where combining picks the maximum severity.
* `maxSeverity` uses `mconcat` to combine the list using the Monoid.
* `main` shows example usage.

---

### 🛠️ How to Run:

Save as `main.hs`, then:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o maxSeverityApp
./maxSeverityApp
```

---
