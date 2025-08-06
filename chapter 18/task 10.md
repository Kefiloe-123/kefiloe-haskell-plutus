HC18T10: nestedFmap Function

```haskell
-- main.hs

-- nestedFmap applies a function to a nested Functor structure.
-- For example, applying (+1) to [[1,2],[3]] should give [[2,3],[4]]
nestedFmap :: (Functor f1, Functor f2) => (a -> b) -> f1 (f2 a) -> f1 (f2 b)
nestedFmap = fmap . fmap
-- This works because fmap . fmap applies the function inside both levels of functors.

-- Main function to demonstrate nestedFmap
main :: IO ()
main = do
  -- Example 1: List of lists of integers
  let listOfLists = [[1, 2], [3, 4]]
  let result1 = nestedFmap (+1) listOfLists
  putStrLn "Applying (+1) to [[1,2],[3,4]]:"
  print result1  -- [[2,3],[4,5]]

  -- Example 2: Maybe with list
  let maybeList = Just [10, 20, 30]
  let result2 = nestedFmap (*2) maybeList
  putStrLn "\nApplying (*2) to Just [10,20,30]:"
  print result2  -- Just [20,40,60]

  -- Example 3: Nothing case
  let nothingList = Nothing :: Maybe [Int]
  let result3 = nestedFmap (*2) nothingList
  putStrLn "\nApplying (*2) to Nothing:"
  print result3  -- Nothing
```

---

### 💡 Explanation:

* `nestedFmap = fmap . fmap` composes two `fmap` calls.

  * The first `fmap` applies to the outer structure (e.g., `Maybe`, `[]`).
  * The second `fmap` applies to the inner structure (e.g., `[]`, again).
* This allows us to map over structures like `[[a]]`, `Maybe [a]`, or even deeper.

---

### 🛠️ How to Run:

Save the code in `main.hs`, then run it:

```bash
runghc main.hs
```

Or compile it:

```bash
ghc main.hs -o nestedFmapApp
./nestedFmapApp
```

---
