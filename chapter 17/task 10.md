HC17T10: Monoid Instance for Config

```haskell
-- main.hs

import Data.Semigroup
import Data.Monoid

-- Define Config data type
data Config = Config
  { loggingLevel :: Int   -- Higher means more verbose
  , timeout      :: Int   -- Timeout in seconds
  , retries      :: Int   -- Number of retries
  } deriving (Show, Eq)

-- Semigroup instance combining fields as specified
instance Semigroup Config where
  Config ll1 t1 r1 <> Config ll2 t2 r2 =
    Config
      (max ll1 ll2)    -- Max logging level
      (min t1 t2)      -- Min timeout
      (max r1 r2)      -- Max retries

-- Monoid instance defining the identity element
instance Monoid Config where
  mempty = Config
    { loggingLevel = 0    -- lowest logging level
    , timeout = 1000      -- highest timeout (example)
    , retries = 0         -- lowest retries
    }
  mappend = (<>)

-- Main function demonstrating the Monoid instance
main :: IO ()
main = do
  let config1 = Config { loggingLevel = 2, timeout = 30, retries = 3 }
      config2 = Config { loggingLevel = 5, timeout = 20, retries = 1 }
      emptyConfig = mempty

      combinedConfig = config1 <> config2
      combinedWithEmpty = config1 <> emptyConfig

  putStrLn "Config 1:"
  print config1

  putStrLn "Config 2:"
  print config2

  putStrLn "Empty Config (mempty):"
  print emptyConfig

  putStrLn "Combined Config (config1 <> config2):"
  print combinedConfig

  putStrLn "Combined Config with mempty (config1 <> mempty):"
  print combinedWithEmpty
```

---

### 💡 Explanation:

* `mempty` is a config with minimal logging level, maximal timeout, minimal retries.
* This ensures `mempty <> x = x` for any config `x`.
* `mappend` is defined as the `Semigroup` operation `<>`.
* `main` shows how combining with `mempty` behaves like identity.

---

### 🛠️ How to Run:

Save as `main.hs`, then:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o configMonoidApp
./configMonoidApp
```

---
