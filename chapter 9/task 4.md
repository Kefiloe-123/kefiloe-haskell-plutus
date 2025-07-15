HC9T4: Extract a Value from a Box

```haskell
-- Define the Box data type
data Box a = Empty | Has a
  deriving Show

-- Function to extract the value from a Box, or use a default
extract :: a -> Box a -> a
extract def Empty   = def
extract _   (Has x) = x

-- Example Boxes
box1 :: Box Int
box1 = Has 42

box2 :: Box Int
box2 = Empty

-- Main function to test extract
main :: IO ()
main = do
  putStrLn "Extract from box1 with default 0:"
  print (extract 0 box1)  -- Should print: 42

  putStrLn "\nExtract from box2 with default 0:"
  print (extract 0 box2)  -- Should print: 0
```

---

### ✅ Example Output:

```
Extract from box1 with default 0:
42

Extract from box2 with default 0:
0
```

---

### ✔️ Explanation:

* `extract def Empty` returns the default.
* `extract _ (Has x)` returns the actual value in the box.
* Works for any type `a`, not just numbers.
