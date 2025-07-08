HC2T5 - Task 5: Defining and Using Functions

```haskell
-- Function to calculate the area of a circle
circleArea :: Float -> Float
circleArea radius = pi * radius * radius

-- Function to find the maximum of three Int values
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree a b c = max a (max b c)

-- Main function to test the above
main :: IO ()
main = do
    -- Test circleArea
    let area1 = circleArea 3.0
    putStrLn ("The area of a circle with radius 3.0 is: " ++ show area1)

    let area2 = circleArea 5.5
    putStrLn ("The area of a circle with radius 5.5 is: " ++ show area2)

    -- Test maxOfThree
    let max1 = maxOfThree 4 7 2
    putStrLn ("The maximum of 4, 7, and 2 is: " ++ show max1)

    let max2 = maxOfThree 10 5 10
    putStrLn ("The maximum of 10, 5, and 10 is: " ++ show max2)

    let max3 = maxOfThree (-3) (-7) (-2)
    putStrLn ("The maximum of -3, -7, and -2 is: " ++ show max3)
```

---

### ▶ **Example Output:**

```
The area of a circle with radius 3.0 is: 28.274334
The area of a circle with radius 5.5 is: 95.03318
The maximum of 4, 7, and 2 is: 7
The maximum of 10, 5, and 10 is: 10
The maximum of -3, -7, and -2 is: -2
```

---

### 🔍 **Explanation:**

| Function     | Input Example | Output Example |
| ------------ | ------------- | -------------- |
| `circleArea` | `3.0`         | `28.274334`    |
| `circleArea` | `5.5`         | `95.03318`     |
| `maxOfThree` | `4, 7, 2`     | `7`            |
| `maxOfThree` | `10, 5, 10`   | `10`           |
| `maxOfThree` | `-3, -7, -2`  | `-2`           |

---

### ✔ **How to Run:**

1. Save as `CircleAndMax.hs`.
2. Compile:

   ```bash
   ghc CircleAndMax.hs
   ```
3. Run:

   ```bash
   ./CircleAndMax
   ```

---
