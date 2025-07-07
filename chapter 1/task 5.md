HC1T5 - Task 5: Laziness in Haskell

* Defines an infinite list of numbers starting from 1.
* Extracts the first `n` numbers using `take`.

---

### ✅ **Haskell Code Example:**

```haskell
-- Define an infinite list of numbers starting from 1
infiniteNumbers :: [Int]
infiniteNumbers = [1..]  -- Equivalent to enumFrom 1

-- Main function to demonstrate taking the first n elements
main :: IO ()
main = do
    putStrLn "Enter how many numbers you want to extract:"
    input <- getLine
    let n = read input :: Int
    let firstN = take n infiniteNumbers
    putStrLn ("The first " ++ show n ++ " numbers are:")
    print firstN
```

---

### ▶ **Example Output:**

```
Enter how many numbers you want to extract:
5
The first 5 numbers are:
[1,2,3,4,5]
```

```
Enter how many numbers you want to extract:
10
The first 10 numbers are:
[1,2,3,4,5,6,7,8,9,10]
```

---

### 🔍 **How It Works:**

* `infiniteNumbers = [1..]` creates an infinite list: `[1, 2, 3, 4, 5, 6, ...]`.
* `take n infiniteNumbers` takes only the first `n` numbers.
* Because of Haskell's **lazy evaluation**, the infinite list is never fully generated—only the first `n` elements are computed.

---

### ✔ **How to Run:**

1. Save this as `InfiniteNumbers.hs`.
2. Compile using GHC:

   ```bash
   ghc InfiniteNumbers.hs
   ```
3. Run the program:

   ```bash
   ./InfiniteNumbers
   ```

---
