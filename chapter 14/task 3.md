HC14T3: NumericUnderscores Extension

```haskell
{-# LANGUAGE NumericUnderscores #-}

-- Main.hs
-- This program demonstrates the use of NumericUnderscores extension.

main :: IO ()
main = do
    let bigNumber1 = 1_000_000      -- One million
        bigNumber2 = 42_000_000_000 -- Forty-two billion
        bigNumber3 = 3_141_592      -- Pi approximation without decimal

    putStrLn $ "Big Number 1: " ++ show bigNumber1
    putStrLn $ "Big Number 2: " ++ show bigNumber2
    putStrLn $ "Big Number 3: " ++ show bigNumber3
```

---

### 💡 Notes:

* The `NumericUnderscores` extension allows you to use underscores in numeric literals to improve readability.
* Underscores are ignored by the compiler, so `1_000_000` is the same as `1000000`.

---

### ▶️ To Run:

If you're using `ghc` directly:

```bash
ghc Main.hs -o bigNumbers && ./bigNumbers
```

Or if you're using a Cabal project:

1. Make sure `main-is: Main.hs` is correct in your `.cabal` file.
2. Build and run:

```bash
cabal build
cabal run
```
