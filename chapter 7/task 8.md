HC7T8: Use Read to parse a value from a string

```haskell
data Shape = Circle Double | Rectangle Double Double
```

```haskell
import Text.Read (readMaybe)

data Shape = Circle Double | Rectangle Double Double deriving Show

-- Parse a Shape from a String safely
parseShape :: String -> Maybe Shape
parseShape input =
  case words input of
    ("Circle":rStr:_) -> do
      r <- readMaybe rStr
      return (Circle r)
    ("Rectangle":wStr:hStr:_) -> do
      w <- readMaybe wStr
      h <- readMaybe hStr
      return (Rectangle w h)
    _ -> Nothing

-- Example main to test the function
main :: IO ()
main = do
  print $ parseShape "Circle 5.0"          -- Just (Circle 5.0)
  print $ parseShape "Rectangle 4.0 6.0"   -- Just (Rectangle 4.0 6.0)
  print $ parseShape "Rectangle 4.0 x"     -- Nothing (invalid height)
  print $ parseShape "Square 3.0"           -- Nothing (unknown shape)
```

---

### Explanation:

* The input string is split into words.
* For `"Circle"` expects one number (radius).
* For `"Rectangle"` expects two numbers (width and height).
* Uses `readMaybe` from `Text.Read` to safely parse numbers, avoiding runtime errors.
* Returns `Nothing` if the format or numbers are invalid.

---

### Sample output:

```
Just (Circle 5.0)
Just (Rectangle 4.0 6.0)
Nothing
Nothing
```

---
