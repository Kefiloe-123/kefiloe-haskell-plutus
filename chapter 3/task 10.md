HC3T10 - Advanced Task 10: Check if a string is a palindrome using recursion and guards

```haskell
-- Function to check if a string is a palindrome using guards and recursion
isPalindrome :: String -> Bool
isPalindrome str
    | length str <= 1 = True
    | head str == last str = isPalindrome (init (tail str))
    | otherwise = False

-- Main function to test isPalindrome
main :: IO ()
main = do
    putStrLn ("isPalindrome \"racecar\": " ++ show (isPalindrome "racecar"))  -- True
    putStrLn ("isPalindrome \"haskell\": " ++ show (isPalindrome "haskell"))  -- False
    putStrLn ("isPalindrome \"madam\": " ++ show (isPalindrome "madam"))      -- True
```

---

### ▶ **Example Output:**

```
isPalindrome "racecar": True
isPalindrome "haskell": False
isPalindrome "madam": True
```

---

### 🔍 **How It Works:**

* If the string length is 0 or 1, it's a palindrome (`True`).
* If the first and last characters are equal, recursively check the middle substring.
* Otherwise, it's not a palindrome (`False`).

---

### ✔ **How to Run:**

1. Save the code as `Palindrome.hs`.
2. Compile:

   ```bash
   ghc Palindrome.hs
   ```
3. Run:

   ```bash
   ./Palindrome
   ```

---
