HC2T2 - Task 2: Function Type Signatures

---

### ✅ **Haskell Code Example:**

```haskell
-- Function that adds two Int values
add :: Int -> Int -> Int
add x y = x + y

-- Function that checks if an Int is even
isEven :: Int -> Bool
isEven x = x `mod` 2 == 0

-- Function that concatenates two Strings
concatStrings :: String -> String -> String
concatStrings s1 s2 = s1 ++ s2

-- Main function to test the above
main :: IO ()
main = do
    -- Test add
    let sumResult = add 5 7
    putStrLn ("The sum of 5 and 7 is: " ++ show sumResult)

    -- Test isEven
    let number = 10
    putStrLn ("Is " ++ show number ++ " even? " ++ show (isEven number))

    -- Test concatStrings
    let combinedString = concatStrings "Hello, " "World!"
    putStrLn ("The concatenated string is: " ++ combinedString)
```

---

### ▶ Example Output:

```
The sum of 5 and 7 is: 12
Is 10 even? True
The concatenated string is: Hello, World!
```

---

### 🔍 **Summary of the Function Signatures:**

| Function        | Type Signature               | Example Call             | Example Result |
| --------------- | ---------------------------- | ------------------------ | -------------- |
| `add`           | `Int -> Int -> Int`          | `add 5 7`                | `12`           |
| `isEven`        | `Int -> Bool`                | `isEven 10`              | `True`         |
| `concatStrings` | `String -> String -> String` | `concatStrings "Hi" "!"` | `"Hi!"`        |

---

### ✔ **How to Run:**

1. Save as `SimpleFunctions.hs`.
2. Compile with GHC:

   ```bash
   ghc SimpleFunctions.hs
   ```
3. Run the program:

   ```bash
   ./SimpleFunctions
   ```

---
