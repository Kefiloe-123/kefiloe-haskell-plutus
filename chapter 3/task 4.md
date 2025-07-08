HC3T4 - Task 4: Calculate the area of a triangle using Heron's formula

```haskell
-- Function to calculate the area of a triangle using Heron's formula
triangleArea :: Float -> Float -> Float -> Float
triangleArea a b c =
    let s = (a + b + c) / 2  -- Semi-perimeter
    in sqrt (s * (s - a) * (s - b) * (s - c))  -- Heron's formula

-- Main function to test triangleArea
main :: IO ()
main = do
    putStrLn ("Area of triangle with sides 3, 4, 5: " ++ show (triangleArea 3 4 5))
    putStrLn ("Area of triangle with sides 7, 8, 9: " ++ show (triangleArea 7 8 9))
```

---

### ▶ **Example Output:**

```
Area of triangle with sides 3, 4, 5: 6.0
Area of triangle with sides 7, 8, 9: 26.832815
```

---

### 🔍 **Explanation of Heron’s Formula:**

$$
s = \frac{a + b + c}{2}
$$

$$
\text{Area} = \sqrt{s \cdot (s - a) \cdot (s - b) \cdot (s - c)}
$$

---

### ✔ **How to Run:**

1. Save the file as `TriangleArea.hs`.
2. Compile the file:

   ```bash
   ghc TriangleArea.hs
   ```
3. Run the executable:

   ```bash
   ./TriangleArea
   ```

---
