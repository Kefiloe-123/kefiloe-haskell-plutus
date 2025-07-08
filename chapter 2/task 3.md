HC2T3 - Task 3: Immutable Variables

---

### ✅ **Correct Haskell Example (Immutable Variables):**

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

-- Main function to print the variables
main :: IO ()
main = do
    putStrLn ("My age is: " ++ show myAge)
    putStrLn ("The value of pi is: " ++ show piValue)
    putStrLn ("Greeting message: " ++ greeting)
    putStrLn ("Is Haskell fun? " ++ show isHaskellFun)
```

---

### ▶ **Correct Example Output:**

```
My age is: 25
The value of pi is: 3.14159
Greeting message: Hello, Haskell!
Is Haskell fun? True
```

---

### ❌ **Incorrect Example (Trying to Modify a Variable):**

If you try to **redefine** a variable, like this:

```haskell
myAge :: Int
myAge = 25

-- Attempt to reassign
myAge = 30
```

You will get an **error like this when compiling:**

```
error:
    Multiple declarations of ‘myAge’
    Declared at: your_file.hs:1:1
                 your_file.hs:4:1
```

This means you **cannot redefine** or reassign `myAge`.

---

### 🔍 **Explanation:**

In Haskell:

* Once a variable is defined, its value **cannot be changed.**
* This is because Haskell is a **purely functional language** where variables represent **values**, not **mutable memory locations**.

If you want a different value, you must **create a new variable with a different name**, e.g.:

```haskell
myAge :: Int
myAge = 25

newAge :: Int
newAge = 30
```

---

### ✔ **How to Run Correct Code:**

1. Save as `ImmutableExample.hs`.
2. Compile:

   ```bash
   ghc ImmutableExample.hs
   ```
3. Run:

   ```bash
   ./ImmutableExample
   ```

---
