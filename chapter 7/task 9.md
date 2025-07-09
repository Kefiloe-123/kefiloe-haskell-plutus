HC7T9: Define a type class with multiple instances

```haskell
-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double deriving Show

-- Define the Describable type class
class Describable a where
  describe :: a -> String

-- Implement Describable for Bool
instance Describable Bool where
  describe True  = "This is True"
  describe False = "This is False"

-- Implement Describable for Shape
instance Describable Shape where
  describe (Circle r) = "A circle with radius " ++ show r
  describe (Rectangle w h) = "A rectangle with width " ++ show w ++ " and height " ++ show h

-- Example main to test
main :: IO ()
main = do
  putStrLn $ describe True
  putStrLn $ describe False
  putStrLn $ describe (Circle 5.0)
  putStrLn $ describe (Rectangle 3.0 4.0)
```

---

### Explanation:

* The `Describable` class declares a method `describe :: a -> String`.
* For `Bool`, `describe` returns a string indicating the Boolean value.
* For `Shape`, it returns a descriptive string with dimensions.

---

### Example output:

```
This is True
This is False
A circle with radius 5.0
A rectangle with width 3.0 and height 4.0
```

---
