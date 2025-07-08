HC4T5 - Task 5: Add a Catch-All Pattern with a Custom Message

```haskell
-- Define the specialBirthday function
specialBirthday :: Int -> String
specialBirthday 1 = "Happy 1st Birthday!"
specialBirthday 16 = "Sweet 16! Enjoy your day!"
specialBirthday 18 = "Congratulations on your 18th Birthday!"
specialBirthday 21 = "Cheers to 21 years!"
specialBirthday 50 = "Happy 50th Birthday! Half a century!"
specialBirthday age = "Happy " ++ show age ++ "th Birthday!"

-- Main function to run some test cases
main :: IO ()
main = do
    putStrLn (specialBirthday 1)
    putStrLn (specialBirthday 16)
    putStrLn (specialBirthday 30)
    putStrLn (specialBirthday 50)
    putStrLn (specialBirthday 75)
```

### ✔️ **Example Output:**

```
Happy 1st Birthday!
Sweet 16! Enjoy your day!
Happy 30th Birthday!
Happy 50th Birthday! Half a century!
Happy 75th Birthday!
```

How it works
specialBirthday :: Int -> String

