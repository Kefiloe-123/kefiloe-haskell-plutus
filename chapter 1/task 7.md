HC1T7 - Task 7: Converting Fahrenheit to Celsius

---

### ✅ **Haskell Code Example:**

```haskell
-- Define the Fahrenheit to Celsius conversion function
fToC :: Floating a => a -> a
fToC f = (f - 32) * 5 / 9

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter temperature in Fahrenheit:"
    input <- getLine
    let fahrenheit = read input :: Double
    let celsius = fToC fahrenheit
    putStrLn ("The temperature in Celsius is: " ++ show celsius)
```

---

### ▶ **Example Output:**

```
Enter temperature in Fahrenheit:
98.6
The temperature in Celsius is: 37.0
```

---

### 🔍 **How It Works:**

* `fToC` is a **pure function** that takes a Fahrenheit temperature and applies the formula:

  $$
  C = \frac{(F - 32) \times 5}{9}
  $$

* The `main` function:

  * Prompts the user to enter a temperature in Fahrenheit.
  * Converts the input string to a `Double`.
  * Calls `fToC` to compute the Celsius equivalent.
  * Prints the result.

---

### ✔ **How to Run:**

1. Save this code as `Temperature.hs`.
2. Compile:

   ```bash
   ghc Temperature.hs
   ```
3. Run the program:

   ```bash
   ./Temperature
   ```

---

