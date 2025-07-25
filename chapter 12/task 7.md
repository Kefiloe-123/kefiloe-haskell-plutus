HC12T7: Calculate Circle Area

```haskell
-- This program defines a function to calculate the area of a circle
-- and demonstrates its usage with user input.

-- Function to calculate the area of a circle
calculateCircleArea :: Floating a => a -> a
calculateCircleArea radius = pi * radius * radius

-- Main function
main :: IO ()
main = do
    putStrLn "Enter the radius of the circle:"
    input <- getLine

    -- Convert input to a floating point number
    let radius = read input :: Double

    -- Calculate the area using the function
    let area = calculateCircleArea radius

    -- Print the result
    putStrLn ("The area of the circle is: " ++ show area)
```

---

### ✅ How to run:

* Paste into an online Haskell compiler like [mycompiler.io](https://www.mycompiler.io/new/haskell)
* Or save locally as `Main.hs` and run:

  ```bash
  ghc Main.hs
  ./Main
  ```

---

### 🧾 Example:

**Input:**

```
Enter the radius of the circle:
5
```

**Output:**

```
The area of the circle is: 78.53981633974483
```
