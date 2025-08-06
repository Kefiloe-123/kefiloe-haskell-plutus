HC15T10: Hybrid Error Handling with Either and IO

```haskell
-- main.hs
-- Demonstrates hybrid error handling using Either and IO exceptions in Haskell

import Control.Exception (catch, IOException)
import System.IO (hFlush, stdout)

-- Pure function to calculate velocity using Either for error handling
calculateVelocity :: Double -> Double -> Either String Double
calculateVelocity _ 0 = Left "Error: Time cannot be zero (division by zero)."
calculateVelocity distance time = Right (distance / time)

-- Function to safely read a Double from user input, catching IO exceptions
safeReadDouble :: String -> IO (Either String Double)
safeReadDouble prompt = catch (do
    putStr prompt
    hFlush stdout
    input <- getLine
    let parsed = reads input :: [(Double, String)]
    return $ case parsed of
        [(val, "")] -> Right val
        _           -> Left "Invalid input. Please enter a numeric value."
    ) handler
  where
    handler :: IOException -> IO (Either String Double)
    handler _ = return $ Left "IO error while reading input."

-- Main program
main :: IO ()
main = do
    putStrLn "Velocity Calculator (distance / time)"
    
    -- Read distance
    distanceResult <- safeReadDouble "Enter distance (in meters): "
    case distanceResult of
        Left err -> putStrLn err
        Right distance -> do
            -- Read time
            timeResult <- safeReadDouble "Enter time (in seconds): "
            case timeResult of
                Left err -> putStrLn err
                Right time -> do
                    -- Use Either to handle division by zero
                    case calculateVelocity distance time of
                        Left errMsg -> putStrLn errMsg
                        Right velocity -> putStrLn $ "Velocity: " ++ show velocity ++ " m/s"
```

---

### 🧪 Example Outputs

**Run 1 – Valid Input**

```
Enter distance (in meters): 100
Enter time (in seconds): 20
Velocity: 5.0 m/s
```

**Run 2 – Invalid Time Input**

```
Enter distance (in meters): 50
Enter time (in seconds): abc
Invalid input. Please enter a numeric value.
```

**Run 3 – Time = 0**

```
Enter distance (in meters): 50
Enter time (in seconds): 0
Error: Time cannot be zero (division by zero).
```

---

### ✅ Summary

| Feature       | Type       | Handled With       |
| ------------- | ---------- | ------------------ |
| Invalid input | IO error   | `catch` & `Either` |
| Division by 0 | Pure error | `Either`           |
