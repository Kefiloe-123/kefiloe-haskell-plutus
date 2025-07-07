HC1T2 - Task 2: Pure Function Example
---

### ✅ **Haskell Code Example:**

```haskell
-- Define a function to calculate the area of a circle
circleArea :: Floating a => a -> a
circleArea radius = pi * radius * radius

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter the radius of the circle:"
    input <- getLine
    let radius = read input :: Double
    let area = circleArea radius
    putStrLn ("The area of the circle with radius " ++ show radius ++ " is " ++ show area)
```

---

### ▶ **Example Output:**

```
Enter the radius of the circle:
5
The area of the circle with radius 5.0 is 78.53981633974483
```

---

### 🔍 **How It Works:**

* **Pure Function:**
  `circleArea` is a **pure function** because:

  * It takes a radius as input.
  * It returns the computed area.
  * It does **not use or modify any external state**.
  * It always returns the same result for the same input.

* **Uses `pi`:**
  Haskell's `pi` constant from the `Prelude` is used.

---

### ℹ️ **How to Run It:**

1. Save as `Circle.hs`.
2. Compile:

   ```bash
   ghc Circle.hs
   ```
3. Run:

   ```bash
   ./Circle
   ```
