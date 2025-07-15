HC9T3: Function to Add Values in a Box

```haskell
-- Define the Box data type
data Box a = Empty | Has a
  deriving Show

-- Function to add a number to the value in the Box (if present)
addN :: Num a => a -> Box a -> Box a
addN _ Empty     = Empty
addN n (Has x)   = Has (x + n)

-- Example Boxes
box1 :: Box Int
box1 = Has 10

box2 :: Box Int
box2 = Empty

-- Main function to test addN
main :: IO ()
main = do
  putStrLn "Adding 5 to box1:"
  print (addN 5 box1)  -- Should print: Has 15

  putStrLn "\nAdding 5 to box2:"
  print (addN 5 box2)  -- Should print: Empty
```

---

### ✅ Example Output:

```
Adding 5 to box1:
Has 15

Adding 5 to box2:
Empty
```

---

### ✔️ Explanation:

* The function `addN` only operates when the box is `Has x`.
* If the box is `Empty`, it leaves it unchanged.
* It works with any numeric type (`Num a =>`), like `Int`, `Float`, etc.
