HC8T6: Define a type Shape using record syntax with fields center :: (Float, Float), color :: String, and radius :: Float for circles, and width :: Float, height :: Float, and color :: String for rectangles. Create an instance of Shape for a circle and a rectangle.


```haskell
-- Define the Shape type with record syntax for Circle and Rectangle
data Shape
  = Circle
      { center :: (Float, Float)
      , radius :: Float
      , color  :: String
      }
  | Rectangle
      { topLeft :: (Float, Float)
      , width   :: Float
      , height  :: Float
      , color   :: String
      }
  deriving Show

-- Create an instance of Shape for a circle
myCircle :: Shape
myCircle = Circle
  { center = (5.0, 10.0)
  , radius = 7.5
  , color  = "Red"
  }

-- Create an instance of Shape for a rectangle
myRectangle :: Shape
myRectangle = Rectangle
  { topLeft = (0.0, 0.0)
  , width   = 20.0
  , height  = 15.0
  , color   = "Blue"
  }

-- Example main to print the shapes
main :: IO ()
main = do
  putStrLn $ "Circle: " ++ show myCircle
  putStrLn $ "Rectangle: " ++ show myRectangle
```

---

### ✅ Example Output:

```
Circle: Circle {center = (5.0,10.0), radius = 7.5, color = "Red"}
Rectangle: Rectangle {topLeft = (0.0,0.0), width = 20.0, height = 15.0, color = "Blue"}
```

---

### ✔️ Explanation:

* `Shape` has **two constructors**, `Circle` and `Rectangle`, each using record syntax.
* The `Circle` constructor has fields `center`, `radius`, and `color`.
* The `Rectangle` constructor has fields `topLeft`, `width`, `height`, and `color`.
* This design makes it easy to work with the individual fields of each shape type.
