HC4T2 - Task 2: Define a dayType Function

```haskell
-- Function to classify a day as a weekend, weekday, or invalid
dayType :: String -> String
dayType "Saturday" = "It's a weekend!"
dayType "Sunday"   = "It's a weekend!"
dayType "Monday"   = "It's a weekday."
dayType "Tuesday"  = "It's a weekday."
dayType "Wednesday"= "It's a weekday."
dayType "Thursday" = "It's a weekday."
dayType "Friday"   = "It's a weekday."
dayType _          = "Invalid day"

-- Main function to test dayType
main :: IO ()
main = do
    putStrLn ("dayType \"Saturday\": " ++ dayType "Saturday")
    putStrLn ("dayType \"Monday\": " ++ dayType "Monday")
    putStrLn ("dayType \"Funday\": " ++ dayType "Funday")
```

---

### ▶ **Example Output:**

```
dayType "Saturday": It's a weekend!
dayType "Monday": It's a weekday.
dayType "Funday": Invalid day
```

---

### 🔍 **How It Works:**

| Day               | Result          |
| ----------------- | --------------- |
| "Saturday"        | It's a weekend! |
| "Sunday"          | It's a weekend! |
| "Monday"-"Friday" | It's a weekday. |
| Any other string  | Invalid day     |

---

### ✔ **How to Run:**

1. Save as `DayType.hs`.
2. Compile:

   ```bash
   ghc DayType.hs
   ```
3. Run:

   ```bash
   ./DayType
   ```

---
