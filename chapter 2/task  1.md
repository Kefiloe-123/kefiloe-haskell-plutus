HC2T1 - Task 1: Checking Types in GHCi

---

### ✅ **Complete Haskell Example:**

```haskell
-- Demonstrate types of various expressions in Haskell

main :: IO ()
main = do
    let intExample :: Int
        intExample = 42
    putStrLn ("42 is an Int: " ++ show intExample)

    let floatExample :: Double
        floatExample = 3.14
    putStrLn ("3.14 is a Double: " ++ show floatExample)

    let stringExample :: String
        stringExample = "Haskell"
    putStrLn ("\"Haskell\" is a String: " ++ stringExample)

    let charExample :: Char
        charExample = 'Z'
    putStrLn ("'Z' is a Char: " ++ show charExample)

    let boolExample :: Bool
        boolExample = True && False
    putStrLn ("True && False is a Bool: " ++ show boolExample)
```

---

### ▶ Example Output:

```
42 is an Int: 42
3.14 is a Double: 3.14
"Haskell" is a String: Haskell
'Z' is a Char: 'Z'
True && False is a Bool: False
```

---

### ℹ️ **Actual Types of the Expressions:**

| Expression      | Type     |
| --------------- | -------- |
| `42`            | `Int`    |
| `3.14`          | `Double` |
| `"Haskell"`     | `String` |
| `'Z'`           | `Char`   |
| `True && False` | `Bool`   |

---

### ✔ **How to Run:**

1. Save this as `TypesDemo.hs`.
2. Compile and run:

   ```bash
   ghc TypesDemo.hs
   ./TypesDemo
   ```

---

### ℹ️ **If using GHCi instead:**

If you are in GHCi, you could type:

```haskell
:t 42
:t 3.14
:t "Haskell"
:t 'Z'
:t True && False
```

You’d get:

```
42 :: Num p => p
3.14 :: Fractional p => p
"Haskell" :: [Char]
'Z' :: Char
True && False :: Bool
```
