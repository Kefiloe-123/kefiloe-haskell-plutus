HC3T7 - Advanced Task 7: Determine the season based on the month using guards

```haskell
-- Function to return the season based on the month number
season :: Int -> String
season month
    | month == 12 || month == 1 || month == 2 = "Winter"
    | month >= 3 && month <= 5                  = "Spring"
    | month >= 6 && month <= 8                  = "Summer"
    | month >= 9 && month <= 11                 = "Autumn"
    | otherwise                                = "Invalid month"

-- Main function to test the season function
main :: IO ()
main = do
    putStrLn ("season 3: " ++ season 3)    -- Spring
    putStrLn ("season 7: " ++ season 7)    -- Summer
    putStrLn ("season 11: " ++ season 11)  -- Autumn
```

---

### ▶ **Example Output:**

```
season 3: Spring
season 7: Summer
season 11: Autumn
```

---

### 🔍 **How It Works:**

* Months 12, 1, 2 → `"Winter"`
* Months 3 to 5 → `"Spring"`
* Months 6 to 8 → `"Summer"`
* Months 9 to 11 → `"Autumn"`
* Any other input → `"Invalid month"`

---

### ✔ **How to Run:**

1. Save this code as `Season.hs`.
2. Compile:

   ```bash
   ghc Season.hs
   ```
3. Run:

   ```bash
   ./Season
   ```

---
