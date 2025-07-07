HC1T1 - Task 1: Function Composition


```haskell
import Text.Read (readMaybe)

-- Define the double function
double :: Int -> Int
double x = x * 2

-- Define the increment function
increment :: Int -> Int
increment x = x + 1

-- Define the composed function using function composition
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double

-- Function to explain how the result is calculated
explain :: Int -> String
explain x =
    let doubled = double x
        incremented = increment doubled
    in  "Step 1: double " ++ show x ++ " = " ++ show doubled ++ "\n"
     ++ "Step 2: increment " ++ show doubled ++ " = " ++ show incremented ++ "\n"
     ++ "Final result: " ++ show incremented

-- Main function with error handling and explanation
main :: IO ()
main = do
    putStrLn "Enter a number:"
    input <- getLine
    case readMaybe input :: Maybe Int of
        Just number -> do
            let result = doubleThenIncrement number
            putStrLn (explain number)
        Nothing -> do
            putStrLn "Invalid input. Please enter a valid integer number."
```

---

### ✅ How This Works:

If you run this program, and **enter a valid number**, it will:

🔸 Double the number and show the step.
🔸 Increment the result and show the step.
🔸 Display the final result.

---

### ▶ Example Output:

```
Enter a number:
4
Step 1: double 4 = 8
Step 2: increment 8 = 9
Final result: 9
```

If the user types something invalid like `"abc"`:

```
Enter a number:
abc
Invalid input. Please enter a valid integer number.
```

---

