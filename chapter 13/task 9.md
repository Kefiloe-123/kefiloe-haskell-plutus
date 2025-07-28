HC13T9: Renaming Module Namespace

```haskell
-- Main.hs
-- Demonstrates renaming module namespaces using `as` and using functions from both

import qualified Data.List as L   -- Rename Data.List as L
import qualified Data.Set  as S   -- Rename Data.Set  as S

main :: IO ()
main = do
  let listA = [1, 2, 3]
  let listB = [3, 4, 5]

  -- Using Data.List functions through alias L
  let combinedList = L.union listA listB
  let sortedList   = L.sort combinedList

  -- Using Data.Set functions through alias S
  let setA = S.fromList listA
  let setB = S.fromList listB
  let combinedSet = S.union setA setB

  putStrLn $ "List union (with duplicates): " ++ show combinedList
  putStrLn $ "Sorted union (list): " ++ show sortedList
  putStrLn $ "Set union (no duplicates): " ++ show (S.toList combinedSet)
```

---

### 🔍 Explanation

* `Data.List` is imported as `L`, so we access `L.union`, `L.sort`, etc.
* `Data.Set` is imported as `S`, so we access `S.union`, `S.fromList`, etc.
* This prevents any naming conflicts and keeps your code readable.

---

### 💡 Output

When you compile and run this with `ghc Main.hs && ./Main`, you should see:

```
List union (with duplicates): [1,2,3,4,5]
Sorted union (list): [1,2,3,4,5]
Set union (no duplicates): [1,2,3,4,5]
```
