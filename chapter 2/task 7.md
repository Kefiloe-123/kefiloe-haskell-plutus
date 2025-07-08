HC2T7 - Task 7: Boolean Expressions

```haskell
-- Main function to evaluate and display boolean expressions
main :: IO ()
main = do
    -- True using &&
    let andTrue = True && True
    putStrLn ("True && True evaluates to: " ++ show andTrue)

    -- False using ||
    let orFalse = False || False
    putStrLn ("False || False evaluates to: " ++ show orFalse)

    -- True using not
    let notFalse = not False
    putStrLn ("not False evaluates to: " ++ show notFalse)

    -- A comparison that returns False
    let comparisonFalse = 5 > 10
    putStrLn ("5 > 10 evaluates to: " ++ show comparisonFalse)
```

---

### ▶ **Example Output:**

```
True && True evaluates to: True
False || False evaluates to: False
not False evaluates to: True
5 > 10 evaluates to: False
```

---

### 🔍 **Summary of Expressions:**

| Expression     | Description              | Result  |                      |       |
| -------------- | ------------------------ | ------- | -------------------- | ----- |
| `True && True` | Both sides are True      | True    |                      |       |
| \`False        |                          | False\` | Both sides are False | False |
| `not False`    | Negates False            | True    |                      |       |
| `5 > 10`       | 5 is not greater than 10 | False   |                      |       |

---

### ✔ **How to Run the Code:**

1. Save this code as `BooleanExpressions.hs`.
2. Compile using GHC:

   ```bash
   ghc BooleanExpressions.hs
   ```
3. Run:

   ```bash
   ./BooleanExpressions
   ```

---
