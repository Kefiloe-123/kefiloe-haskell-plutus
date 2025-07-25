HC12T5: Palindrome Checker

```haskell
-- This program checks if a given string is a palindrome.
-- It defines a function isPalindrome and tests it using user input.

-- Function to check if a string is a palindrome
isPalindrome :: String -> Bool
isPalindrome str = str == reverse str

-- Main function
main :: IO ()
main = do
    putStrLn "Enter a string:"
    input <- getLine

    if isPalindrome input
        then putStrLn "Yes, it's a palindrome!"
        else putStrLn "No, it's not a palindrome."
```

---

### ✅ How to run this:

* **In an online Haskell compiler** (like [mycompiler.io](https://www.mycompiler.io)):

  1. Paste the code.
  2. Click **Run**.

* **Locally using GHC**:

  1. Save as `Main.hs`
  2. Run:

     ```bash
     ghc Main.hs
     ./Main
     ```

---

### 🧾 Example:

**Input:**

```
madam
```

**Output:**

```
Yes, it's a palindrome!
```

---
