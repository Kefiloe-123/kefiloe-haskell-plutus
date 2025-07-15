 HC9T2: Implement a Parametric Data Type

```haskell
-- Define the Box data type
data Box a = Empty | Has a
  deriving Show

-- Example instances of Box
emptyBox :: Box Int
emptyBox = Empty

fullBox :: Box String
fullBox = Has "A treasure"

-- Main function to test the Box values
main :: IO ()
main = do
  putStrLn "Empty box:"
  print emptyBox

  putStrLn "\nFull box:"
  print fullBox
```

---

### ✅ Example Output:

```
Empty box:
Empty

Full box:
Has "A treasure"
```

---

### ✔️ Explanation:

* `Box a` is a **generic** data type that works with any type `a`.
* `Empty` represents an empty box.
* `Has a` wraps a value of type `a` inside the box.
* `deriving Show` allows the values to be printed easily.
