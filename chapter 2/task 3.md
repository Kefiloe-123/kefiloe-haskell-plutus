HC2T3 - Task 3: Immutable Variables

---

### ✅ **Complete Haskell Example:**

```haskell
-- Immutable variable definitions
myAge :: Int
myAge = 25

piValue :: Double
piValue = 3.14159

greeting :: String
greeting = "Hello, Haskell!"

isHaskellFun :: Bool
isHaskellFun = True

-- Main function to display the values
main :: IO ()
main = do
    putStrLn ("My age is: " ++ show myAge)
    putStrLn ("The value of pi is: " ++ show piValue)
    putStrLn ("Greeting message: " ++ greeting)
    putStrLn ("Is Haskell fun? " ++ show isHaskellFun)
```

---

### ▶ Example Output:

```
My age is: 25
The value of pi is: 3.14159
Greeting message: Hello, Haskell!
Is Haskell fun? True
```

---

### 🔍 **Explanation of the Variable Types:**

| Variable Name  | Type     | Example Value     |
| -------------- | -------- | ----------------- |
| `myAge`        | `Int`    | 25                |
| `piValue`      | `Double` | 3.14159           |
| `greeting`     | `String` | "Hello, Haskell!" |
| `isHaskellFun` | `Bool`   | True              |

---

### ✔ **How to Run the Program:**

1. Save as `ImmutableVars.hs`.
2. Compile it using GHC:

   ```bash
   ghc ImmutableVars.hs
   ```
3. Run the program:

   ```bash
   ./ImmutableVars
   ```

---
