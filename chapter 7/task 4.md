HC7T4: Create a custom type and implement Show and Read

```haskell
-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double

-- Show instance for Shape
instance Show Shape where
  show (Circle r) = "Circle " ++ show r
  show (Rectangle w h) = "Rectangle " ++ show w ++ " " ++ show h

-- Read instance for Shape
instance Read Shape where
  readsPrec _ input =
    case words input of
      ("Circle":r:rest) ->
        [(Circle (read r), unwords rest)]
      ("Rectangle":w:h:rest) ->
        [(Rectangle (read w) (read h), unwords rest)]
      _ -> []  -- fail to parse if input doesn't match

-- Example main to test Show and Read
main :: IO ()
main = do
  let c = Circle 5.0
      r = Rectangle 4.0 6.0

  putStrLn $ "Circle: " ++ show c
  putStrLn $ "Rectangle: " ++ show r

  -- Example of reading shapes from strings
  let circleStr = "Circle 7.5"
      rectStr   = "Rectangle 3.0 8.0"

  let parsedCircle = read circleStr :: Shape
  let parsedRect   = read rectStr :: Shape

  putStrLn $ "Parsed Circle: " ++ show parsedCircle
  putStrLn $ "Parsed Rectangle: " ++ show parsedRect
```

---

### ✅ Example Output:

```
Circle: Circle 5.0
Rectangle: Rectangle 4.0 6.0
Parsed Circle: Circle 7.5
Parsed Rectangle: Rectangle 3.0 8.0
```

---

### ✔️ Explanation:

* **`Show` instance:** Converts a `Shape` into a string like `"Circle 5.0"` or `"Rectangle 4.0 6.0"`.
* **`Read` instance:** Parses a string like `"Circle 7.5"` or `"Rectangle 3.0 8.0"` back into a `Shape`.
* `readsPrec` handles basic parsing by splitting the input with `words`.

---
