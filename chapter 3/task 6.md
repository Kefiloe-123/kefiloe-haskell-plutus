HC3T6 - Advanced Task 6: Check leap year using if-then-else

```haskell
-- Function to check if a year is a leap year
isLeapYear :: Int -> Bool
isLeapYear year =
    if year `mod` 400 == 0 then True
    else if year `mod` 100 == 0 then False
    else if year `mod` 4 == 0 then True
    else False

-- Main function to test isLeapYear
main :: IO ()
main = do
    putStrLn ("isLeapYear 2000: " ++ show (isLeapYear 2000))  -- True
    putStrLn ("isLeapYear 1900: " ++ show (isLeapYear 1900))  -- False
    putStrLn ("isLeapYear 2024: " ++ show (isLeapYear 2024))  -- True
```

---

### ▶ **Example Output:**

```
isLeapYear 2000: True
isLeapYear 1900: False
isLeapYear 2024: True
```

---

### 🔍 **How It Works:**

* If divisible by 400 → leap year (`True`).
* Else if divisible by 100 but not 400 → not a leap year (`False`).
* Else if divisible by 4 → leap year (`True`).
* Otherwise → not a leap year (`False`).

---

### ✔ **How to Run:**

1. Save as `LeapYear.hs`.
2. Compile:

   ```bash
   ghc LeapYear.hs
   ```
3. Run:

   ```bash
   ./LeapYear
   ```

---
