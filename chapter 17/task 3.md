HC17T3: Monoid Instance for Severity

```haskell
-- main.hs

import Data.Semigroup
import Data.Monoid

-- Define Severity data type with four levels
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord)

-- Semigroup instance: combine by taking the max (higher severity wins)
instance Semigroup Severity where
    (<>) = max

-- Monoid instance: identity is Low (lowest severity)
instance Monoid Severity where
    mempty = Low
    mappend = (<>)

-- Main function to demonstrate usage
main :: IO ()
main = do
    let sev1 = Low
        sev2 = High
        sev3 = mempty  -- Should be Low
        sev4 = Critical

    putStrLn $ "Low <> High = " ++ show (sev1 <> sev2)
    putStrLn $ "Medium <> mempty = " ++ show (Medium <> sev3)
    putStrLn $ "mempty <> Critical = " ++ show (sev3 <> sev4)
    putStrLn $ "mempty = " ++ show (mempty :: Severity)
```

---

### 💡 Explanation:

* `Semigroup` instance defines `<>` as `max`.
* `Monoid` instance defines `mempty = Low`.
* `mappend` is defaulted to `<>` (from `Semigroup`).
* `main` demonstrates combining with identity.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o severityMonoid
./severityMonoid
```

---
