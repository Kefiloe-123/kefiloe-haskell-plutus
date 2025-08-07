HC20T9: replicateMonad with Identity Monad

```haskell
-- main.hs
-- Demonstrates replicating a value using the Identity monad.

import Control.Monad.Identity

-- replicateMonad takes a value and replicates it n times using Identity monad
replicateMonad :: Int -> a -> Identity [a]
replicateMonad n x = return (replicate n x)
-- Alternatively: replicateM n (return x) :: Identity [a]

-- Main function demonstrating replicateMonad
main :: IO ()
main = do
  -- Run the Identity monad
  let result = runIdentity (replicateMonad 5 "Hello")
  -- Print the replicated result
  print result
```

---

### 💡 Explanation

* **`Identity` monad** is a simple monad that does nothing special—it's often used for testing or generic monadic interfaces.
* `replicateMonad` uses `return` to wrap a list into the `Identity` monad.
* You can also use `replicateM n (return x)` for the same effect with more generality.

---

### 🛠️ How to Run

Save the code in a file called `main.hs`, then run it with:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o replicate
./replicate
```

---

### ✅ Output

```
["Hello","Hello","Hello","Hello","Hello"]
```

