HC5T3: Checking for Uppercase Letters

```haskell
import Data.Char (isUpper)

-- Function to check if any word starts with uppercase
startsWithUppercase :: [String] -> Bool
startsWithUppercase = any (\word -> not (null word) && isUpper (head word))

-- Example main to test the function
main :: IO ()
main = do
    print $ startsWithUppercase ["hello", "world"]         -- Output: False
    print $ startsWithUppercase ["hello", "World"]         -- Output: True
    print $ startsWithUppercase ["", "empty", "Apple"]     -- Output: True
    print $ startsWithUppercase []                          -- Output: False
```

---

### How it works:

* `any` takes a predicate and a list, returns `True` if **any element satisfies** the predicate.
* Predicate here checks:

  * The word is **not empty** (`not (null word)`)
  * The **first character** (`head word`) is uppercase (`isUpper`).

---

### Sample output:

```
False
True
True
False
```
