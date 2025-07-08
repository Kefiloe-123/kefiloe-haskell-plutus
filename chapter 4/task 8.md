HC4T8 - Task 8: Extract Values from Tuples

```haskell
-- Define the describeTuple function
describeTuple :: (Show a, Show b) => (a, b) -> String
describeTuple (x, y) = "The first element is " ++ show x ++ " and the second element is " ++ show y ++ "."

-- Main function to test describeTuple
main :: IO ()
main = do
    putStrLn (describeTuple (42, "apple"))       -- Output: The first element is 42 and the second element is "apple".
    putStrLn (describeTuple ("Hello", True))     -- Output: The first element is "Hello" and the second element is True.
    putStrLn (describeTuple (3.14, 99))          -- Output: The first element is 3.14 and the second element is 99.
```

---

## ✅ **How It Works**

### Function Definition:

```haskell
describeTuple :: (Show a, Show b) => (a, b) -> String
```

* **`(a, b)`** is the input tuple.
* **`Show a, Show b`** constraints allow the tuple's values to be converted to strings using `show`.

### Pattern Matching:

```haskell
describeTuple (x, y) = ...
```

It destructures the tuple into **`x`** and **`y`** and builds a descriptive string.

---

## ▶️ **Example Output:**

```
The first element is 42 and the second element is "apple".
The first element is "Hello" and the second element is True.
The first element is 3.14 and the second element is 99.
```

---
