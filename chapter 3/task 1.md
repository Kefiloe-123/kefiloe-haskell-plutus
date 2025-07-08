HC3T1 - Task 1: Check if a number is positive, negative, or zero

```haskell
-- Function to check whether a number is positive, negative, or zero
checkNumber :: Int -> String
checkNumber n =
    if n > 0 then "Positive"
    else if n < 0 then "Negative"
    else "Zero"

-- Main function to test checkNumber with different values
main :: IO ()
main = do
    putStrLn ("checkNumber 5: " ++ checkNumber 5)
    putStrLn ("checkNumber (-3): " ++ checkNumber (-3))
    putStrLn ("checkNumber 0: " ++ checkNumber 0)
```

---

### ▶ **Example Output:**

```
checkNumber 5: Positive
checkNumber (-3): Negative
checkNumber 0: Zero
```

---

### 🔍 **How It Works:**

* `if n > 0 then "Positive"`: If the number is greater than 0, return `"Positive"`.
* `else if n < 0 then "Negative"`: If the number is less than 0, return `"Negative"`.
* `else "Zero"`: Otherwise (if it's neither greater nor less than 0), return `"Zero"`.

---

### ✔ **How to Run:**

1. Save this code as `CheckNumber.hs`.
2. Compile it:

   ```bash
   ghc CheckNumber.hs
   ```
3. Run the program:

   ```bash
   ./CheckNumber
   ```

---
