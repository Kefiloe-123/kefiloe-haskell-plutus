HC5T1: Using applyTwice

```haskell
-- Define the applyThrice function
applyThrice :: (Int -> Int) -> Int -> Int
applyThrice f x = f (f (f x))

-- Example functions to test
double :: Int -> Int
double n = 2 * n

increment :: Int -> Int
increment n = n + 1

-- Main function to test applyThrice
main :: IO ()
main = do
    print (applyThrice double 1)    -- Output: 8 (double 1 three times: 1 → 2 → 4 → 8)
    print (applyThrice increment 5) -- Output: 8 (increment 5 three times: 5 → 6 → 7 → 8)
```

---

## ✅ **How It Works**

### Function Signature:

```haskell
applyThrice :: (Int -> Int) -> Int -> Int
```

* Takes a **function from Int to Int** and an **integer**.
* Returns an **integer**.

### Function Body:

```haskell
applyThrice f x = f (f (f x))
```

* It applies the function `f` to `x`, then applies it again to the result, and once more.

---

## ▶️ **Example Output:**

```
8
8
```

---
