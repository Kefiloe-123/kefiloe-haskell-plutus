HC3T2 - Task 2: Determine the grade based on a score using guards

```haskell
-- Function to classify scores into grades using guards
grade :: Int -> String
grade score
    | score >= 90 = "A"
    | score >= 80 = "B"
    | score >= 70 = "C"
    | score >= 60 = "D"
    | otherwise   = "F"

-- Main function to test the grade function
main :: IO ()
main = do
    putStrLn ("Grade for 95: " ++ grade 95)
    putStrLn ("Grade for 72: " ++ grade 72)
    putStrLn ("Grade for 50: " ++ grade 50)
```

---

### ▶ **Example Output:**

```
Grade for 95: A
Grade for 72: C
Grade for 50: F
```

---

### 🔍 **How It Works:**

| Guard                  | Returns |
| ---------------------- | ------- |
| `score >= 90`          | `"A"`   |
| `score >= 80`          | `"B"`   |
| `score >= 70`          | `"C"`   |
| `score >= 60`          | `"D"`   |
| `otherwise` (below 60) | `"F"`   |

* Guards check each condition from top to bottom until one matches.
* `otherwise` is equivalent to `True`, covering all other cases.

---

### ✔ **How to Run:**

1. Save the code as `Grade.hs`.
2. Compile it:

   ```bash
   ghc Grade.hs
   ```
3. Run the program:

   ```bash
   ./Grade
   ```

---
