HC7T2: Implement an Ord instance for a custom data type

```
Red < Green < Blue
```

### Complete Example:

```haskell
-- Define the Color data type
data Color = Red | Green | Blue

-- Eq instance for Color
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

-- Ord instance for Color, defining the order Red < Green < Blue
instance Ord Color where
  compare Red   Red   = EQ
  compare Red   _     = LT
  compare Green Red   = GT
  compare Green Green = EQ
  compare Green Blue  = LT
  compare Blue  Blue  = EQ
  compare Blue  _     = GT

-- Example main to test comparisons
main :: IO ()
main = do
  print (Red < Green)   -- True
  print (Green < Blue)  -- True
  print (Red < Blue)    -- True
  print (Blue < Red)    -- False
```

### ✅ Example Output:

```
True
True
True
False
```

---

### ✔️ Alternative simplified approach using `fromEnum`:

If you'd prefer a **shorter version**, you could use this approach:

```haskell
-- Define the Color data type
data Color = Red | Green | Blue

-- Eq and Show instances
instance Eq Color where
  Red == Red = True
  Green == Green = True
  Blue == Blue = True
  _ == _ = False

instance Show Color where
  show Red = "Red"
  show Green = "Green"
  show Blue = "Blue"

-- Ord instance using assigned numeric values
instance Ord Color where
  compare c1 c2 = compare (colorToInt c1) (colorToInt c2)

colorToInt :: Color -> Int
colorToInt Red = 1
colorToInt Green = 2
colorToInt Blue = 3
```

Both versions will work correctly. ✅
