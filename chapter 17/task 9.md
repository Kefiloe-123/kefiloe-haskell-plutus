HC17T9: Config Data Type and Semigroup Instance

```haskell
-- main.hs

import Data.Semigroup

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

-- Main function demonstrating the Semigroup instance
main :: IO ()
main = do
  let config1 = Config { loggingLevel = 2, timeout = 30, retries = 3 }
      config2 = Config { loggingLevel = 5, timeout = 20, retries = 1 }

      combinedConfig = config1 <> config2

  putStrLn "Config 1:"
  print config1

  putStrLn "Config 2:"
  print config2

  putStrLn "Combined Config (max loggingLevel & retries, min timeout):"
  print combinedConfig
```

---

### 💡 Explanation:

* The `Semigroup` instance uses `max` for `loggingLevel` and `retries` and `min` for `timeout`.
* `main` shows two example configs and their combined result.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o configApp
./configApp
```

---
