HC11T1: Greet the User

```haskell
-- Greeting.hs

main :: IO ()
main = do
  putStrLn "What is your name?"
  name <- getLine
  putStrLn ("Hello, " ++ name ++ "!")
```

### How to Run It

1. Save the code in a file named `Greeting.hs`.

2. Compile it using GHC or run it with `runhaskell`:

   ```bash
   runhaskell Greeting.hs
   ```

3. You'll see:

   ```
   What is your name?
   ```

   After entering a name like `Alice`, you'll get:

   ```
   Hello, Alice!
   ```

