HC4T3 - Task 3: Define a gradeComment Function

```haskell
-- Define the function
gradeComment :: Int -> String
gradeComment grade
  | grade >= 90 && grade <= 100 = "Excellent!"
  | grade >= 70 && grade <= 89  = "Good job!"
  | grade >= 50 && grade <= 69  = "You passed."
  | grade >= 0 && grade <= 49   = "Better luck next time."
  | otherwise                   = "Invalid grade"

-- Main function to test the gradeComment function
main :: IO ()
main = do
  putStrLn $ "Grade 95: " ++ gradeComment 95
  putStrLn $ "Grade 75: " ++ gradeComment 75
  putStrLn $ "Grade 55: " ++ gradeComment 55
  putStrLn $ "Grade 30: " ++ gradeComment 30
  putStrLn $ "Grade -5: " ++ gradeComment (-5)
  putStrLn $ "Grade 105: " ++ gradeComment 105
```

### ✅ How to run:

1. Save this code in a file named `Grade.hs`.
2. Open your terminal and navigate to the directory containing the file.
3. Run it with GHCi:

   ```bash
   ghci Grade.hs
   ```
4. In GHCi, type:

   ```haskell
   main
   ```

### ✔️ Example Output:

```
Grade 95: Excellent!
Grade 75: Good job!
Grade 55: You passed.
Grade 30: Better luck next time.
Grade -5: Invalid grade
Grade 105: Invalid grade
```
