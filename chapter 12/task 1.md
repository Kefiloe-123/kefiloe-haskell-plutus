HC12T1: Print a Welcome Message

```haskell
-- This program prints a welcome message to the terminal.

main :: IO ()
main = do
    putStrLn "Welcome to Haskell Programming!"
```

### ✅ How to run:

If you're using a local setup with GHC:

1. Save the code above in a file named `Main.hs`.
2. In the terminal, run:

   ```bash
   ghc Main.hs
   ./Main
   ```

If you're using an online Haskell compiler like [Replit](https://replit.com/) or [Haskell Online Compiler](https://www.mycompiler.io/), just paste the code and click **Run**.
