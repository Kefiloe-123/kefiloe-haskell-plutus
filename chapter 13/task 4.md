HC13T4: SumNonEmpty Module

```haskell
-- File: SumNonEmpty.hs
-- This module defines a function `sumNonEmpty` which sums a non-empty list.
-- If the list is empty, it throws an error.

module SumNonEmpty where

-- sumNonEmpty: sums a non-empty list; throws an error on empty list
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error "Error: List is empty. Cannot compute sum."
sumNonEmpty xs = sum xs
```

---

### ✅ Example with `main` Function:

To run and test `sumNonEmpty`, you can create a separate file or add the following `main` block *after the module* or in a separate script (e.g., `Main.hs`):

```haskell
-- File: Main.hs
-- This is a demonstration of how to use the SumNonEmpty module

import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
  let list1 = [3, 5, 7]
  let list2 = []
  
  putStrLn $ "Sum of [3,5,7]: " ++ show (sumNonEmpty list1)

  -- This line will cause a runtime error since the list is empty
  putStrLn $ "Sum of []: " ++ show (sumNonEmpty list2)
```

---

### 🔧 How to Run This

1. Save the first part as `SumNonEmpty.hs`.
2. Save the second part as `Main.hs`.
3. Compile and run using:

   ```bash
   ghc Main.hs
   ./Main
   ```

---

### 💡 Output:

```
Sum of [3,5,7]: 15
*** Exception: Error: List is empty. Cannot compute sum.
```
