HC3T5 - Task 5: Determine the type of a triangle using guards

```haskell
-- Function to classify a triangle based on its sides
triangleType :: Float -> Float -> Float -> String
triangleType a b c
    | a == b && b == c = "Equilateral"
    | a == b || b == c || a == c = "Isosceles"
    | otherwise = "Scalene"

-- Main function to test triangleType
main :: IO ()
main = do
    putStrLn ("triangleType 3 3 3: " ++ triangleType 3 3 3)  -- Equilateral
    putStrLn ("triangleType 5 5 8: " ++ triangleType 5 5 8)  -- Isosceles
    putStrLn ("triangleType 6 7 8: " ++ triangleType 6 7 8)  -- Scalene
```

---

### ▶ **Example Output:**

```
triangleType 3 3 3: Equilateral
triangleType 5 5 8: Isosceles
triangleType 6 7 8: Scalene
```

---

### 🔍 **How It Works:**

* `a == b && b == c`: All sides equal → **Equilateral**
* `a == b || b == c || a == c`: Two sides equal → **Isosceles**
* Otherwise → **Scalene**

---

### ✔ **How to Run:**

1. Save as `TriangleType.hs`.
2. Compile:

   ```bash
   ghc TriangleType.hs
   ```
3. Run:

   ```bash
   ./TriangleType
   ```

---
