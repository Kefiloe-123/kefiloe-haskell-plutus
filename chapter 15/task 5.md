HC15T5: Safe Division Using Maybe

```haskell
-- main.hs
-- Safe division using Maybe to avoid divide-by-zero errors

import System.IO (hFlush, stdout)
import Text.Read (readMaybe)

-- Safe division function: returns Nothing if denominator is zero
safeDivide :: Double -> Double -> Maybe Double
safeDivide _ 0 = Nothing
safeDivide num denom = Just (num / denom)

-- Prompt and safely parse a Double using readMaybe
getDouble :: String -> IO (Maybe Double)
getDouble prompt = do
    putStr prompt
    hFlush stdout
    input <- getLine
    return (readMaybe input)

-- Main function
main :: IO ()
main = do
    putStrLn "Safe Division Program Using Maybe"

    mNum   <- getDouble "Enter numerator: "
    mDenom <- getDouble "Enter denominator: "

    let result = do
            num   <- mNum
            denom <- mDenom
            safeDivide num denom

    case result of
        Nothing    -> putStrLn "Error: Invalid input or division by zero."
        Just value -> putStrLn $ "Result: " ++ show value
```

---

### 🧪 Example Runs

✅ **Valid Input**

```
Enter numerator: 10
Enter denominator: 2
Result: 5.0
```

❌ **Divide by Zero**

```
Enter numerator: 15
Enter denominator: 0
Error: Invalid input or division by zero.
```

❌ **Invalid Input**

```
Enter numerator: abc
Enter denominator: 4
Error: Invalid input or division by zero.
```

---

### ✅ Summary

| Situation       | Output                                 |
| --------------- | -------------------------------------- |
| Valid division  | `Just result` printed                  |
| Denominator = 0 | Graceful error message using `Nothing` |
| Invalid input   | Also handled using `Nothing`           |
