HC2T6 - Task 6: Understanding Int vs Integer

```haskell
-- Define an Int variable with 2^62
smallNumber :: Int
smallNumber = 2 ^ 62

-- Define an Integer variable with 2^127
bigNumber :: Integer
bigNumber = 2 ^ 127

main :: IO ()
main = do
    putStrLn ("Small number (2^62) as Int: " ++ show smallNumber)
    putStrLn ("Big number (2^127) as Integer: " ++ show bigNumber)

    -- Attempt to evaluate 2^64 as Int
    let overflowExample = (2 ^ 64) :: Int
    putStrLn ("Attempting 2^64 as Int (likely overflow): " ++ show overflowExample)
```

---

### ▶ **Example Output on a Typical 64-bit System:**

```
Small number (2^62) as Int: 4611686018427387904
Big number (2^127) as Integer: 170141183460469231731687303715884105728
Attempting 2^64 as Int (likely overflow): 0
```

> ⚠️ **Explanation of the Overflow:**

* On most 64-bit systems, `Int` is **bounded to 64 bits**, so `2^64` exceeds the maximum for an `Int`.
* You’ll likely see an **incorrect value** (often `0`, a negative number, or a wraparound value) because of overflow.

---

### ✔ **Key Takeaways:**

| Expression           | Type      | Expected Value                                   |
| -------------------- | --------- | ------------------------------------------------ |
| `2 ^ 62 :: Int`      | `Int`     | ✅ Works correctly. Fits in 64 bits.              |
| `2 ^ 127 :: Integer` | `Integer` | ✅ Works correctly. `Integer` has no upper limit. |
| `2 ^ 64 :: Int`      | `Int`     | ⚠️ Overflows. Result is wrong on most systems.   |

---

### ✔ **How to Run:**

1. Save this as `PowerDemo.hs`.
2. Compile and run:

   ```bash
   ghc PowerDemo.hs
   ./PowerDemo
   ```

---

### ➕ **Optional GHCi Test:**

In **GHCi**, type:

```haskell
Prelude> 2^64 :: Int
```

On most systems, you'll see:

```haskell
0
```

➡️ Because `2^64` **overflows the Int type**.

---
