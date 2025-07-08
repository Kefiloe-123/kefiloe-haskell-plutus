HC4T7 - Task 7: Ignore Elements in a List

```haskell
-- Define the firstAndThird function
firstAndThird :: [a] -> [a]
firstAndThird (x:_:z:_) = [x, z]  -- Matches at least 3 elements, picks the first and third
firstAndThird (x:_)     = [x]     -- Only the first element exists
firstAndThird []        = []      -- Empty list

-- Main function to test the code
main :: IO ()
main = do
    print (firstAndThird [10, 20, 30, 40])   -- Output: [10,30]
    print (firstAndThird ["a", "b", "c", "d"]) -- Output: ["a","c"]
    print (firstAndThird [1, 2])             -- Output: [1]
    print (firstAndThird [])                 -- Output: []
```

---

## ✅ **How It Works**

| List Pattern | Meaning                                                | Return   |
| ------------ | ------------------------------------------------------ | -------- |
| `(x:_:z:_)`  | At least 3 elements → take the first `x` and third `z` | `[x, z]` |
| `(x:_)`      | At least 1 element → take the first `x`                | `[x]`    |
| `[]`         | Empty list                                             | `[]`     |

---

## ▶️ **Example Output:**

```
[10,30]
["a","c"]
[1]
[]
```

---
