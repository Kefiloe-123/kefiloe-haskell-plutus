HC7T1: Implement an Eq instance for a custom data type

```haskell
-- Define the Color data type
data Color = Red | Green | Blue

-- Manually implement the Eq type class for Color
instance Eq Color where
  Red   == Red   = True
  Green == Green = True
  Blue  == Blue  = True
  _     == _     = False

-- Show instance for easy printing
instance Show Color where
  show Red   = "Red"
  show Green = "Green"
  show Blue  = "Blue"

-- Example main to test equality
main :: IO ()
main = do
  let color1 = Red
      color2 = Green
      color3 = Red

  putStrLn $ "Is " ++ show color1 ++ " equal to " ++ show color2 ++ "? " ++ show (color1 == color2)
  putStrLn $ "Is " ++ show color1 ++ " equal to " ++ show color3 ++ "? " ++ show (color1 == color3)
```

### Explanation:

* `Color` is a custom data type with three constructors: `Red`, `Green`, and `Blue`.
* The `Eq` instance defines how to compare two `Color` values.
* The `Show` instance is defined to make the colors display nicely when printed.

### Example output when running the code:

```
Is Red equal to Green? False
Is Red equal to Red? True
```

---
