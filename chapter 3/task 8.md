HC3T8 - Advanced Task 8: Calculate BMI and return category using where

```haskell
-- Function to classify BMI category
bmiCategory :: Float -> Float -> String
bmiCategory weight height
    | bmi < 18.5             = "Underweight"
    | bmi <= 24.9            = "Normal"
    | bmi <= 29.9            = "Overweight"
    | otherwise              = "Obese"
  where
    bmi = weight / (height ^ 2)

-- Main function to test bmiCategory
main :: IO ()
main = do
    putStrLn ("BMI category for 70kg and 1.75m: " ++ bmiCategory 70 1.75)
    putStrLn ("BMI category for 90kg and 1.8m: " ++ bmiCategory 90 1.8)
```

---

### ▶ **Example Output:**

```
BMI category for 70kg and 1.75m: Normal
BMI category for 90kg and 1.8m: Overweight
```

---

### 🔍 **How It Works:**

* `bmi` is calculated using `weight / (height^2)` in the `where` clause.
* Guards classify the BMI into four categories.

---

### ✔ **How to Run:**

1. Save the file as `BMICategory.hs`.
2. Compile with GHC:

   ```bash
   ghc BMICategory.hs
   ```
3. Run:

   ```bash
   ./BMICategory
   ```

---
