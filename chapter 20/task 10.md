HC20T10: Nested StateT and MaybeT Transformer

```haskell
-- main.hs
-- Demonstrates combining StateT and MaybeT monads

import Control.Monad.Trans.State
import Control.Monad.Trans.Maybe
import Control.Monad.Trans.Class (lift)
import Control.Monad (guard)

-- Define a type alias for the nested monad transformer
type MyMonad = MaybeT (State Int)

-- A function that increments the state but fails if the state exceeds a limit
safeIncrement :: Int -> MyMonad ()
safeIncrement limit = do
  current <- lift get         -- Get current state from StateT
  let next = current + 1
  guard (next <= limit)       -- Fail (Nothing) if limit exceeded
  lift (put next)             -- Update the state if within limit

-- Runs a sequence of increments, stopping if the limit is reached
runIncrements :: MyMonad ()
runIncrements = do
  safeIncrement 5
  safeIncrement 5
  safeIncrement 5
  safeIncrement 5
  safeIncrement 5
  safeIncrement 5 -- This one should fail when state reaches 6

-- Main function
main :: IO ()
main = do
  let initialState = 0
      result = runState (runMaybeT runIncrements) initialState
  print result
```

---

### 💡 Explanation

* `StateT Int` tracks an integer state.
* `MaybeT` allows failure: if `guard (next <= limit)` fails, the whole computation short-circuits with `Nothing`.
* `runState (runMaybeT ...)` unwraps both transformers.

---

### 🛠️ How to Run

Save as `main.hs`, then:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o nested
./nested
```

---

### ✅ Output

```
(Nothing,5)
```

This means:

* The computation failed (`Nothing`) because we tried to increment past the limit.
* The last successful state before failure was `5`.

---
