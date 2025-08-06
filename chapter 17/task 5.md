HC17T5: combineLists Function

```haskell
-- main.hs

import Data.Semigroup

-- Define a function that combines two lists using Semigroup (<>)
combineLists :: [Int] -> [Int] -> [Int]
combineLists xs ys = xs <> ys
-- Lists have a Semigroup instance where (<>) is list concatenation (++)

-- Main function to demonstrate combineLists
main :: IO ()
main = do
    let list1 = [1, 2, 3]
        list2 = [4, 5, 6]

    let combined = combineLists list1 list2

    putStrLn $ "List 1: " ++ show list1
    putStrLn $ "List 2: " ++ show list2
    putStrLn $ "Combined list: " ++ show combined
```

---

### 💡 Explanation:

* The `Semigroup` instance for lists uses `(++)` for `(<>)`.
* `combineLists` simply uses `(<>)` to concatenate two lists.
* `main` demonstrates combining two example lists.

---

### 🛠️ How to Run:

Save as `main.hs`, then run with:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o combineListsApp
./combineListsApp
```
