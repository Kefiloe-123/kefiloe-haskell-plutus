HC14T4: TypeApplications Extension

```haskell
{-# LANGUAGE TypeApplications #-}

-- Main.hs
-- This program demonstrates using TypeApplications to convert a String to an Int.

import Text.Read (readMaybe)

-- Convert a string to an Int using read with type application
stringToInt :: String -> Maybe Int
stringToInt str = readMaybe @Int str

main :: IO ()
main = do
    putStrLn "Enter a number:"
    input <- getLine
    case stringToInt input of
        Just n  -> putStrLn $ "You entered: " ++ show n
        Nothing -> putStrLn "That was not a valid number."
```

---

### 💡 Explanation:

* `{-# LANGUAGE TypeApplications #-}` enables the `@Int` syntax for specifying types.
* `readMaybe @Int str` safely parses the string to an `Int`, returning `Nothing` on failure.
* The use of `Maybe Int` helps avoid crashing if the input is not a valid number.

---

### ▶️ How to Run:

If you're using `ghc`:

```bash
ghc Main.hs -o convert && ./convert
```

If you're using a Cabal project, ensure your `.cabal` file includes:

```cabal
build-depends: base >=4.7 && <5, text, containers
```

Then run:

```bash
cabal build
cabal run
```
