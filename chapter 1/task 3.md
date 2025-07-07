HC1T3 - Task 3: Checking if a Number is Greater than 18

---

### ✅ **Haskell Code Example:**

```haskell
-- Define the greaterThan18 function
greaterThan18 :: Int -> Bool
greaterThan18 x = x > 18

-- Main function to test the greaterThan18 function with different values
main :: IO ()
main = do
    let value1 = 10
    putStrLn ("Is " ++ show value1 ++ " greater than 18? " ++ show (greaterThan18 value1))

    let value2 = 18
    putStrLn ("Is " ++ show value2 ++ " greater than 18? " ++ show (greaterThan18 value2))

    let value3 = 25
    putStrLn ("Is " ++ show value3 ++ " greater than 18? " ++ show (greaterThan18 value3))

    let value4 = 19
    putStrLn ("Is " ++ show value4 ++ " greater than 18? " ++ show (greaterThan18 value4))

    let value5 = 5
    putStrLn ("Is " ++ show value5 ++ " greater than 18? " ++ show (greaterThan18 value5))
```

---

### ▶ **Example Output:**

```
Is 10 greater than 18? False
Is 18 greater than 18? False
Is 25 greater than 18? True
Is 19 greater than 18? True
Is 5 greater than 18? False
```

---

### 🔍 **How It Works:**

* `greaterThan18` is a **pure Boolean function** that simply checks if the input is greater than 18 (`x > 18`).
* The `main` function tests several hard-coded values (**10, 18, 25, 19, 5**) and prints whether each one is greater than 18.

---

### ✔ How to Run:

1. Save this as `GreaterThan18.hs`.
2. Compile it:

   ```bash
   ghc GreaterThan18.hs
   ```
3. Run the executable:

   ```bash
   ./GreaterThan18
   ```

---
