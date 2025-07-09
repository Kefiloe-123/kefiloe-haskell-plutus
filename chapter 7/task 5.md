HC7T5: Implement a function that uses Num constraints

```haskell
-- Function to calculate the area of a square
squareArea :: Num a => a -> a
squareArea side = side * side

-- Example main to test the function
main :: IO ()
main = do
  putStrLn $ "The area of a square with side 5 is: " ++ show (squareArea 5)
  putStrLn $ "The area of a square with side 3.2 is: " ++ show (squareArea 3.2)
```

---

### ✅ Example Output:

```
The area of a square with side 5 is: 25
The area of a square with side 3.2 is: 10.240000000000002
```

---

### ✔️ Explanation:

* The type signature `Num a => a -> a` allows the function to work with **any numeric type**, such as `Int`, `Float`, `Double`, etc.
* The area of a square is calculated using the formula:
  **area = side × side**

---
