HC4T6 - Task 6: Identify List Contents Using Pattern Matching

```haskell
-- Define the whatsInsideThisList function
whatsInsideThisList :: [a] -> String
whatsInsideThisList []       = "The list is empty."
whatsInsideThisList [_]      = "The list has one element."
whatsInsideThisList [_, _]   = "The list has two elements."
whatsInsideThisList (_:_:_:_) = "The list has more than two elements."

-- Main function to run some examples
main :: IO ()
main = do
    putStrLn (whatsInsideThisList ([] :: [Int]))       -- The list is empty.
    putStrLn (whatsInsideThisList [42])                -- The list has one element.
    putStrLn (whatsInsideThisList ["apple", "banana"]) -- The list has two elements.
    putStrLn (whatsInsideThisList [1, 2, 3, 4])       -- The list has more than two elements.
```

---

## ✅ **How it Works**

* `[]`: Pattern matches an **empty list**, returns `"The list is empty."`.
* `[_]`: Matches a list with **one element**, using `_` to ignore the element itself.
* `[_, _]`: Matches a list with **exactly two elements**.
* `(_:_:_:_)`: Matches a list with **three or more elements**, ignores their values.

---

## ▶️ **Example Output:**

```
The list is empty.
The list has one element.
The list has two elements.
The list has more than two elements.
```

---
