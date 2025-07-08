HC2T4 - Task 4: Converting Between Infix and Prefix Notations

```haskell
main :: IO ()
main = do
    putStrLn "=== Infix to Prefix ==="
    let result1 = (+) 5 3   -- Prefix for 5 + 3
    putStrLn ("(+) 5 3 = " ++ show result1)

    let result2 = (*) 10 4  -- Prefix for 10 * 4
    putStrLn ("(*) 10 4 = " ++ show result2)

    let result3 = (&&) True False  -- Prefix for True && False
    putStrLn ("(&&) True False = " ++ show result3)

    putStrLn "\n=== Prefix to Infix ==="
    let result4 = 7 + 2
    putStrLn ("7 + 2 = " ++ show result4)

    let result5 = 6 * 5
    putStrLn ("6 * 5 = " ++ show result5)

    let result6 = True && False
    putStrLn ("True && False = " ++ show result6)
```

---

### ▶ **Example Output:**

```
=== Infix to Prefix ===
(+) 5 3 = 8
(*) 10 4 = 40
(&&) True False = False

=== Prefix to Infix ===
7 + 2 = 9
6 * 5 = 30
True && False = False
```

---

### 🔍 **Summary of the Syntax:**

| Expression Type | Example         | Haskell Syntax    |
| --------------- | --------------- | ----------------- |
| Infix           | `5 + 3`         | `5 + 3`           |
| Prefix          |                 | `(+) 5 3`         |
| Infix           | `10 * 4`        | `10 * 4`          |
| Prefix          |                 | `(*) 10 4`        |
| Infix           | `True && False` | `True && False`   |
| Prefix          |                 | `(&&) True False` |

---

### ✔ **How to Run:**

1. Save this as `NotationDemo.hs`.
2. Compile using GHC:

   ```bash
   ghc NotationDemo.hs
   ```
3. Run:

   ```bash
   ./NotationDemo
   ```

---
