HC20T6: doubleMonad Combining Maybe and List

```haskell
-- main.hs

-- Function that doubles each element inside a Maybe list
doubleMonad :: Num a => Maybe [a] -> Maybe [a]
doubleMonad mx = do
  xs <- mx              -- Unwrap the Maybe
  return (map (*2) xs)  -- Use map to double each element

-- Alternatively, using fmap + map:
-- doubleMonad = fmap (map (*2))

-- Main function to test doubleMonad
main :: IO ()
main = do
  let example1 = Just [1, 2, 3]
      example2 = Nothing

  putStrLn "Doubling elements in Maybe [Int]:"
  print $ doubleMonad example1  -- Output: Just [2,4,6]
  print $ doubleMonad example2  -- Output: Nothing
```

---

### 💡 Explanation:

* `Maybe` is used to represent optional values (could be `Nothing`).
* `[a]` is a list of values.
* `doubleMonad`:

  * Uses a `do` block to unwrap the `Maybe [a]`.
  * Applies `map (*2)` to double each number in the list.
  * Wraps the result back in `Just`.

---

### 🛠️ How to Run

Save this code to a file called `main.hs`, then run:

```bash
runghc main.hs
```

---
