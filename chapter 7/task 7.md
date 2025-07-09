HC7T7: Implement a function using Bounded and Enum


```haskell
data Color = Red | Green | Blue
```

```haskell
-- Color data type
data Color = Red | Green | Blue deriving (Show, Eq)

-- Function to get the next color with wrap-around
nextColor :: Color -> Color
nextColor Red   = Green
nextColor Green = Blue
nextColor Blue  = Red

-- Example main to test the function
main :: IO ()
main = do
  print $ nextColor Red    -- Should print Green
  print $ nextColor Green  -- Should print Blue
  print $ nextColor Blue   -- Should print Red
```

---

### Explanation:

* Pattern matching is used to define the next color for each constructor.
* When `Blue` is passed, it wraps back to `Red`.

---

### Example output:

```
Green
Blue
Red
```

---
