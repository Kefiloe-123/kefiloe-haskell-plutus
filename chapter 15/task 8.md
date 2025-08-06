HC15T8: Division with Either for Detailed Errors

```haskell
-- main.hs
-- Division using Either to return detailed error messages

import System.IO (hFlush, stdout)

-- Safe division function with detailed error messages
safeDivide :: Double -> Double -> Either String Double
safeDivide _ 0 = Left "Error: Cannot divide by zero."
safeDivide num denom
    | isNaN num = Left "Error: Numerator is not a number."
    | isNaN denom = Left "Error: Denominator is not a number."
    | otherwise = Right (num / denom)

-- Function to read and validate a Double from user input
readDouble :: String -> IO (Either String Double)
readDouble prompt = do
    putStr prompt
    hFlush stdout
    input <- getLine
    let parsed = reads input :: [(Double, String)]
    return $ case parsed of
        [(val, "")] -> Right val
        _           -> Left "Invalid input. Please enter a valid number."

-- Main function
main :: IO ()
main = do
    putStrLn "Safe Division Calculator"

    -- Read numerator
    numResult <- readDouble "Enter numerator: "
    case numResult of
        Left err -> putStrLn err
        Right numerator -> do

            -- Read denominator
            denomResult <- readDouble "Enter denominator: "
            case denomResult of
                Left err -> putStrLn err
                Right denominator -> do

                    -- Perform division with Either handling
                    case safeDivide numerator denominator of
                        Left errMsg -> putStrLn errMsg
                        Right result -> putStrLn $ "Result: " ++ show result
```

---

### 🧪 Example Outputs

✅ **Valid input**

```
Enter numerator: 10
Enter denominator: 2
Result: 5.0
```

❌ **Division by zero**

```
Enter numerator: 5
Enter denominator: 0
Error: Cannot divide by zero.
```

❌ **Invalid input**

```
Enter numerator: abc
Invalid input. Please enter a valid number.
```

---

### ✅ Summary

| Condition       | Result                                |
| --------------- | ------------------------------------- |
| Valid division  | `Right result`                        |
| Denominator = 0 | `Left "Error: Cannot divide by zero"` |
| Invalid input   | `Left "Invalid input..."`             |
