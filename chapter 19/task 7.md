HC19T7: conditionalPrint with when

```haskell
-- main.hs

import Control.Monad (when)

-- conditionalPrint prints the given message only if the condition is True
conditionalPrint :: Bool -> String -> IO ()
conditionalPrint cond msg = when cond $ putStrLn msg

-- Main function to demonstrate conditionalPrint
main :: IO ()
main = do
  putStrLn "Testing conditionalPrint with True condition:"
  conditionalPrint True "This message should be printed."

  putStrLn "\nTesting conditionalPrint with False condition:"
  conditionalPrint False "This message should NOT be printed."
```

---

### 💡 Explanation:

* `when` takes a `Bool` and an `IO` action.
* It runs the action only if the condition is `True`.
* Otherwise, it does nothing.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o conditionalPrintApp
./conditionalPrintApp
```

---
