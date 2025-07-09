HC7T6: Use the Integral and Floating type classes

```haskell
-- Import for pi constant (optional as pi is in Prelude)
import Prelude

-- circleCircumference works for any Real type (Integral or Floating)
circleCircumference :: Real a => a -> Double
circleCircumference r = 2 * pi * realToFrac r

-- Example main to test the function
main :: IO ()
main = do
  putStrLn $ "Circumference with radius 5 (Int): " ++ show (circleCircumference (5 :: Int))
  putStrLn $ "Circumference with radius 3.2 (Double): " ++ show (circleCircumference 3.2)
```

---

### Explanation:

* The type signature uses `Real a => a -> Double`, so it accepts any type that's an instance of `Real` (which includes `Int`, `Integer`, `Float`, `Double`).
* `realToFrac` converts the input to a `Double` for the calculation.
* Uses the formula: circumference = 2 × π × radius

---

### Example output:

```
Circumference with radius 5 (Int): 31.41592653589793
Circumference with radius 3.2 (Double): 20.106192982974676
```

---
