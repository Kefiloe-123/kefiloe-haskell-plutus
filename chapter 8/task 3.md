HC8T3: Define a type Shape with constructors Circle Float and Rectangle Float Float. Create a function area :: Shape -> Float that calculates the area of the shape. Calculate the area of a circle with radius 5 and a rectangle with sides 10 and 5.

```haskell
-- Define the Shape data type
data Shape = Circle Float | Rectangle Float Float deriving Show

-- Function to calculate the area of a Shape
area :: Shape -> Float
area (Circle r) = pi * r * r
area (Rectangle w h) = w * h

-- Example main to test the area function
main :: IO ()
main = do
  let circleArea = area (Circle 5)
  let rectangleArea = area (Rectangle 10 5)

  putStrLn $ "Area of Circle with radius 5: " ++ show circleArea
  putStrLn $ "Area of Rectangle with sides 10 and 5: " ++ show rectangleArea
```

---

### ✅ Example Output:

```
Area of Circle with radius 5: 78.53982
Area of Rectangle with sides 10 and 5: 50.0
```

---

### ✔️ Explanation:

* `Shape` has two constructors: `Circle` taking one `Float`, and `Rectangle` taking two `Float`s.
* `area` matches on the shape and calculates:

  * Circle area: $\pi \times r^2$
  * Rectangle area: $\text{width} \times \text{height}$
* In `main`, it calculates and prints the areas.
