HC15T6: Safe Input Parsing with readMaybe

```haskell
-- main.hs
-- Demonstrates safe input parsing using readMaybe from Text.Read

import System.IO (hFlush, stdout)
import Text.Read (readMaybe)

-- Function to calculate velocity safely
calculateVelocity :: Double -> Double -> Maybe Double
calculateVelocity _ 0 = Nothing  -- Prevent division by zero
calculateVelocity distance time = Just (distance / time)

-- Function to prompt and safely read a Double using readMaybe
getDouble :: String -> IO (Maybe Double)
getDouble prompt = do
    putStr prompt
    hFlush stdout
    input <- getLine
    return (readMaybe input)

-- Main program
main :: IO ()
main = do
    putStrLn "Velocity Calculator (using readMaybe for safe input parsing)"

    mDistance <- getDouble "Enter distance (in meters): "
    mTime     <- getDouble "Enter time (in seconds): "

    let mVelocity = do
            distance <- mDistance
            time     <- mTime
            calculateVelocity distance time

    case mVelocity of
        Nothing  -> putStrLn "Error: Invalid input or division by zero."
        Just vel -> putStrLn $ "Velocity: " ++ show vel ++ " m/s"
```

---

### 🧪 Example Runs

✅ **Valid Input**

```
Enter distance (in meters): 100
Enter time (in seconds): 25
Velocity: 4.0 m/s
```

❌ **Invalid Number**

```
Enter distance (in meters): ten
Enter time (in seconds): 5
Error: Invalid input or division by zero.
```

❌ **Division by Zero**

```
Enter distance (in meters): 50
Enter time (in seconds): 0
Error: Invalid input or division by zero.
```

---

### ✅ Summary

| Error Type       | Handled By    |
| ---------------- | ------------- |
| Invalid input    | `readMaybe`   |
| Division by zero | `Maybe` logic |
