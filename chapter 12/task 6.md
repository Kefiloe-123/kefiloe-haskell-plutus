HC12T6: Sort a List of Integers

```haskell
-- This program reads a list of integers from the user,
-- sorts them in ascending order, and prints the result.

import Data.List (sort)  -- Import sort function

-- Main function
main :: IO ()
main = do
    putStrLn "Enter a list of integers separated by spaces:"
    input <- getLine

    -- Split the input into words, convert to integers
    let numbers = map read (words input) :: [Int]

    -- Sort the list
    let sortedNumbers = sort numbers

    -- Print the sorted list
    putStrLn "Sorted list in ascending order:"
    print sortedNumbers
```

---

### ✅ How to run:

* Paste this into [https://www.mycompiler.io/new/haskell](https://www.mycompiler.io/new/haskell) or any online Haskell editor and press **Run**.
* Or locally:

  ```bash
  ghc Main.hs
  ./Main
  ```

---

### 🧾 Example:

**Input:**

```
Enter a list of integers separated by spaces:
34 7 12 1 9
```

**Output:**

```
Sorted list in ascending order:
[1,7,9,12,34]
```

---
