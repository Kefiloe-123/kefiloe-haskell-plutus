HC9T5: Parametric Data Type with Record Syntax

```haskell
-- Define the parametric Shape data type
data Shape a
  = Circle a Float              -- Circle with color and radius
  | Rectangle a Float Float     -- Rectangle with color, width, and height
  deriving Show

-- Example shapes using String as color
circle1 :: Shape String
circle1 = Circle "Red" 10.0

rectangle1 :: Shape String
rectangle1 = Rectangle "Blue" 5.0 3.0

-- Main function to print the shapes
main :: IO ()
main = do
  putStrLn "Circle:"
  print circle1

  putStrLn "\nRectangle:"
  print rectangle1
```

---

### ✅ Example Output:

```
Circle:
Circle "Red" 10.0

Rectangle:
Rectangle "Blue" 5.0 3.0
```

---

### ✔️ Explanation:

* `Shape a` is parametric, meaning the color can be of **any type** (e.g., `String`, custom `Color` type, etc.).
* `Circle a Float`: stores a color of type `a` and a radius.
* `Rectangle a Float Float`: stores a color of type `a`, width, and height.
* `deriving Show` allows printing with `print`.

