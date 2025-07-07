HC1T8 - Task 8: Higher-Order Functions

---

### ✅ **Haskell Code Example:**

```haskell
-- Define the applyTwice function
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)

-- Example functions to test applyTwice
double :: Int -> Int
double x = x * 2

increment :: Int -> Int
increment x = x + 1

-- Main function to demonstrate applyTwice
main :: IO ()
main = do
    let result1 = applyTwice double 3
    putStrLn ("Applying double twice to 3 gives: " ++ show result1)
    -- double(double(3)) = double(6) = 12

    let result2 = applyTwice increment 5
    putStrLn ("Applying increment twice to 5 gives: " ++ show result2)
    -- increment(increment(5)) = increment(6) = 7

    let result3 = applyTwice reverse "hello"
    putStrLn ("Applying reverse twice to \"hello\" gives: " ++ show result3)
    -- reverse(reverse("hello")) = "hello"
```

---

### ▶ **Example Output:**

```
Applying double twice to 3 gives: 12
Applying increment twice to 5 gives: 7
Applying reverse twice to "hello" gives: "hello"
```

---

### 🔍 **How It Works:**

| Function Call                | What Happens                           | Final Result |
| ---------------------------- | -------------------------------------- | ------------ |
| `applyTwice double 3`        | double(double(3)) → double(6)          | 12           |
| `applyTwice increment 5`     | increment(increment(5)) → increment(6) | 7            |
| `applyTwice reverse "hello"` | reverse(reverse("hello")) → "hello"    | "hello"      |

* `applyTwice` works on **any function and input type** where the function and value match.

---

### ✔ **How to Run:**

1. Save this as `ApplyTwice.hs`.
2. Compile:

   ```bash
   ghc ApplyTwice.hs
   ```
3. Run:

   ```bash
   ./ApplyTwice
   ```

---
