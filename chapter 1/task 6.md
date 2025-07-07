HC1T6 - Task 6: Using Type Signatures

---

### ✅ **Haskell Code Example:**

```haskell
-- Define the addNumbers function
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter the first number:"
    input1 <- getLine
    putStrLn "Enter the second number:"
    input2 <- getLine
    let num1 = read input1 :: Int
    let num2 = read input2 :: Int
    let result = addNumbers num1 num2
    putStrLn ("The sum of " ++ show num1 ++ " and " ++ show num2 ++ " is " ++ show result)
```

---

### ▶ **Example Output:**

```
Enter the first number:
5
Enter the second number:
8
The sum of 5 and 8 is 13
```

---

### 🔍 **How It Works:**

* The function `addNumbers` is a **pure function**:
  It takes two integers as input and returns their sum.
* The `main` function:

  * Prompts the user for two numbers.
  * Converts the input from strings to integers using `read`.
  * Calls `addNumbers`.
  * Prints the result.

---

### ✔ **How to Run:**

1. Save as `AddNumbers.hs`.
2. Compile:

   ```bash
   ghc AddNumbers.hs
   ```
3. Run:

   ```bash
   ./AddNumbers
   ```

---
