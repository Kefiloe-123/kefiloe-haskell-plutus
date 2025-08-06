HC15T4: Exception Handler for Traffic Light

```haskell
-- main.hs
-- Demonstrates exception handling with a custom TrafficLightException and a handler function

import Control.Exception
import System.IO (hFlush, stdout)

-- Define custom TrafficLightException
data TrafficLightException = RedLightException
    deriving (Show)

-- Make it an instance of the Exception class
instance Exception TrafficLightException

-- Function that simulates car behavior based on traffic light
reactToTrafficLight :: String -> IO ()
reactToTrafficLight light = case light of
    "green"  -> putStrLn "Proceed: Green light!"
    "yellow" -> putStrLn "Slow down: Yellow light!"
    "red"    -> throwIO RedLightException  -- Throw custom exception
    _        -> putStrLn "Unknown traffic light color."

-- Handler function for TrafficLightException
handleTrafficLight :: TrafficLightException -> IO ()
handleTrafficLight _ = putStrLn "Stop! Red light encountered. Exception handled."

-- Main function
main :: IO ()
main = do
    putStr "Enter traffic light color (green, yellow, red): "
    hFlush stdout
    color <- getLine

    -- Try to react to traffic light and handle exception if red
    reactToTrafficLight color `catch` handleTrafficLight
```

---

### 🧪 Example Runs

✅ **Green Light**

```
Enter traffic light color (green, yellow, red): green
Proceed: Green light!
```

✅ **Yellow Light**

```
Enter traffic light color (green, yellow, red): yellow
Slow down: Yellow light!
```

❌ **Red Light (Handled Exception)**

```
Enter traffic light color (green, yellow, red): red
Stop! Red light encountered. Exception handled.
```

---

### ✅ Summary

| Input       | Output                                          |
| ----------- | ----------------------------------------------- |
| `"green"`   | Proceed: Green light!                           |
| `"yellow"`  | Slow down: Yellow light!                        |
| `"red"`     | Stop! Red light encountered. Exception handled. |
| `"unknown"` | Unknown traffic light color.                    |
