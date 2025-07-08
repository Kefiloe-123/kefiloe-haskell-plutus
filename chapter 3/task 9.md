HC3T9 - Advanced Task 9: Find the maximum of three numbers using let

```haskell
-- Function to find the maximum of three Int values using let bindings
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree a b c =
    let maxAB = max a b
        maxABC = max maxAB c
    in maxABC

-- Main function to test maxOfThree
main :: IO ()
main = do
    putStrLn ("maxOfThree 10 20 15: " ++ show (maxOfThree 10 20 15))
    putStrLn ("maxOfThree 5 25 10: " ++ show (maxOfThree 5 25 10))
```

---

### ▶ **Example Output:**

```
maxOfThree 10 20 15: 20
maxOfThree 5 25 10: 25
```

---

### 🔍 **Explanation:**

* `maxAB` stores the maximum of `a` and `b`.
* `maxABC` stores the maximum of `maxAB` and `c`.
* The final result is `maxABC`.

---

### ✔ **How to Run:**

1. Save this code as `MaxOfThree.hs`.
2. Compile:

   ```bash
   ghc MaxOfThree.hs
   ```
3. Run:

   ```bash
   ./MaxOfThree
   ```

---
