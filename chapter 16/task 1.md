HC16T1: Reverse a String

```haskell
-- main.hs

-- Define a function that reverses a string
reverseString :: String -> String
reverseString str = reverse str

-- The main function to run the program
main :: IO ()
main = do
    -- Define the input string
    let original = "Hello, Haskell!"
    
    -- Call the reverseString function
    let reversed = reverseString original
    
    -- Print the original and reversed strings
    putStrLn ("Original: " ++ original)
    putStrLn ("Reversed: " ++ reversed)
```

---

### 💡 How to Run:

1. Save the code above in a file called `main.hs`.
2. Compile or run it with:

   ```bash
   runghc main.hs
   ```

   or compile with:

   ```bash
   ghc main.hs -o reverseApp
   ./reverseApp
   ```
