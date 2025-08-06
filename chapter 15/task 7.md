HC15T7: Velocity Calculation with Optionals and Parsing Handling

```haskell
-- main.hs
-- Calculate velocity using Maybe to handle optional values and parsing errors

import System.IO (hFlush, stdout)

-- Function to safely parse a Double from String
parseDouble :: String -> Maybe Double
parseDouble input =
    case reads input :: [(Double, String)] of
        [(val, "")] -> Just val
        _           -> Nothing

-- Safe velocity calculation: velocity = distance / time
-- Returns Nothing if time is 0
calculateVelocity :: Double -> Double -> Maybe Double
calculateVelocity _ 0 = Nothing
calculateVelocity distance time = Just (distance / time)

-- Prompt the user and get a valid Double using Maybe
getDouble :: String -> IO (Maybe Double)
getDouble prompt = do
    putStr prompt
    hFlush stdout
    input <- getLine
    return $ parseDouble input

-- Main function
main :: IO ()
main = do
    putStrLn "Velocity Calculator (distance / time) with Maybe error handling"

    mDistance <- getDouble "Enter distance (in meters): "
    mTime     <- getDouble "Enter time (in seconds): "

    -- Combine Maybe values using do-notation
    let mVelocity = do
            distance <- mDistance
            time     <- mTime
            calculateVelocity distance time

    -- Display result
    case mVelocity of
        Nothing -> putStrLn "Error: Invalid input or division by zero."
        Just v  -> putStrLn $ "Velocity: " ++ show v ++ " m/s"
```

---

### 🧪 Example Outputs

✅ **Valid input**

```
Enter distance (in meters): 100
Enter time (in seconds): 20
Velocity: 5.0 m/s
```

❌ **Time = 0**

```
Enter distance (in meters): 50
Enter time (in seconds): 0
Error: Invalid input or division by zero.
```

❌ **Invalid input**

```
Enter distance (in meters): hello
Enter time (in seconds): 10
Error: Invalid input or division by zero.
```

---

### ✅ Summary

| Situation            | Output                               |
| -------------------- | ------------------------------------ |
| Valid inputs         | Shows calculated velocity            |
| Invalid number input | Shows error using `Nothing` handling |
| Time = 0             | Gracefully reports error             |
