HC7T10: Use a function with multiple type class constraints

To write `describeAndCompare` that takes **two Describable values** and returns the description of the **larger one**, we need to ensure the values can be compared.

That means the type must be an instance of **both `Describable` and `Ord`**.

```haskell
-- Define the Shape data type with Eq and Ord instances
data Shape = Circle Double | Rectangle Double Double deriving (Show, Eq)

-- Define Ord for Shape by comparing their areas
instance Ord Shape where
  compare (Circle r1) (Circle r2) = compare (areaCircle r1) (areaCircle r2)
  compare (Rectangle w1 h1) (Rectangle w2 h2) = compare (areaRect w1 h1) (areaRect w2 h2)
  -- Define order between Circle and Rectangle by comparing their areas
  compare s1 s2 = compare (area s1) (area s2)

areaCircle :: Double -> Double
areaCircle r = pi * r * r

areaRect :: Double -> Double -> Double
areaRect w h = w * h

area :: Shape -> Double
area (Circle r) = areaCircle r
area (Rectangle w h) = areaRect w h

-- Describable type class
class Describable a where
  describe :: a -> String

-- Implement Describable for Shape
instance Describable Shape where
  describe (Circle r) = "Circle with radius " ++ show r
  describe (Rectangle w h) = "Rectangle " ++ show w ++ " x " ++ show h

-- Implement Describable for Int (for example)
instance Describable Int where
  describe x = "Int: " ++ show x

-- compareAndDescribe function
describeAndCompare :: (Describable a, Ord a) => a -> a -> String
describeAndCompare x y
  | x >= y    = describe x
  | otherwise = describe y

-- Example main
main :: IO ()
main = do
  let c1 = Circle 3.0
      c2 = Circle 4.0
      r1 = Rectangle 2.0 5.0
      r2 = Rectangle 3.0 3.0

  putStrLn $ describeAndCompare c1 c2   -- Larger circle by area
  putStrLn $ describeAndCompare r1 r2   -- Larger rectangle by area
  putStrLn $ describeAndCompare 5 10    -- Larger Int
```

---

### Explanation:

* `describeAndCompare` takes two values of the same type that implement **both** `Describable` and `Ord`.
* It compares them and returns the description of the larger one.
* For `Shape`, `Ord` is defined based on the area.
* I added an example `Describable` instance for `Int` for demonstration.

---

### Sample output:

```
Circle with radius 4.0
Rectangle 2.0 x 5.0
Int: 10
```

---
