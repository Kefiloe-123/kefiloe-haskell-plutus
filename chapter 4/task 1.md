HC4T1 - Task 1: Define a weatherReport Function

```haskell
-- Function to return a message based on the weather condition
weatherReport :: String -> String
weatherReport "sunny"  = "It's a bright and beautiful day!"
weatherReport "rainy"  = "Don't forget your umbrella!"
weatherReport "cloudy" = "A bit gloomy, but no rain yet!"
weatherReport _        = "Weather unknown"

-- Main function to test weatherReport
main :: IO ()
main = do
    putStrLn ("weatherReport \"sunny\": " ++ weatherReport "sunny")
    putStrLn ("weatherReport \"rainy\": " ++ weatherReport "rainy")
    putStrLn ("weatherReport \"cloudy\": " ++ weatherReport "cloudy")
    putStrLn ("weatherReport \"snowy\": " ++ weatherReport "snowy")
```

---

### ▶ **Example Output:**

```
weatherReport "sunny": It's a bright and beautiful day!
weatherReport "rainy": Don't forget your umbrella!
weatherReport "cloudy": A bit gloomy, but no rain yet!
weatherReport "snowy": Weather unknown
```

---

### 🔍 **How It Works:**

* Matches `"sunny"`, `"rainy"`, and `"cloudy"` exactly.
* For any other input (`_`), returns `"Weather unknown"`.

---

### ✔ **How to Run:**

1. Save the file as `WeatherReport.hs`.
2. Compile it:

   ```bash
   ghc WeatherReport.hs
   ```
3. Run it:

   ```bash
   ./WeatherReport
   ```

---

