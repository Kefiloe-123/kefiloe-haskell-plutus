HC4T4 - Task 4: Rewrite specialBirthday using Pattern Matching

```haskell
-- Define the function using pattern matching
specialBirthday :: Int -> String
specialBirthday 1   = "Happy 1st Birthday!"
specialBirthday 18  = "Congratulations on becoming an adult!"
specialBirthday 100 = "Wow! A century old!"
specialBirthday age = "Happy Birthday! You are " ++ show age ++ " years old."

-- Main function to test specialBirthday
main :: IO ()
main = do
  putStrLn $ specialBirthday 1
  putStrLn $ specialBirthday 18
  putStrLn $ specialBirthday 100
  putStrLn $ specialBirthday 25
  putStrLn $ specialBirthday 50
```

### ✔️ How to run:

1. Save this in a file called `Birthday.hs`.
2. Open the terminal, navigate to the folder with the file, and run:

   ```bash
   ghci Birthday.hs
   ```
3. Then type:

   ```haskell
   main
   ```

### ▶️ Example Output:

```
Happy 1st Birthday!
Congratulations on becoming an adult!
Wow! A century old!
Happy Birthday! You are 25 years old.
Happy Birthday! You are 50 years old.
```

---

