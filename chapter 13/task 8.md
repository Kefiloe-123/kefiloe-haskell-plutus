HC13T8: Qualified Imports for Name Conflicts

```haskell
-- Main.hs
-- Demonstrates handling name conflicts using qualified imports

import qualified Data.List as List
import qualified Data.Set as Set

main :: IO ()
main = do
  let list1 = [1, 2, 3]
  let list2 = [3, 4, 5]
  let set1  = Set.fromList list1
  let set2  = Set.fromList list2

  -- List union (allows duplicates)
  let listUnion = List.union list1 list2

  -- Set union (removes duplicates automatically)
  let setUnion = Set.union set1 set2

  putStrLn $ "List union: " ++ show listUnion
  putStrLn $ "Set union: " ++ show (Set.toList setUnion)
```

---

### 🧠 Explanation

* `import qualified Data.List as List`: allows you to use `List.union`.
* `import qualified Data.Set as Set`: allows you to use `Set.union`.
* This prevents conflict between two different `union` functions.

---

### 💻 How to Run

```bash
ghc Main.hs
./Main
```

---

### 📝 Example Output

```
List union: [1,2,3,4,5]
Set union: [1,2,3,4,5]
```
