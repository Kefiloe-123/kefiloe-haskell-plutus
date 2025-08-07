HC20T16: retryIO with IO Monad

```haskell
-- main.hs
-- This program defines a retryIO function that retries a failing IO action.

import Control.Exception (try, SomeException)
import System.IO

-- retryIO retries a given IO operation up to 'n' times if it throws an exception
retryIO :: Int -> IO a -> IO (Maybe a)
retryIO 0 action = do
    putStrLn "All attempts failed."
    return Nothing
retryIO n action = do
    result <- try action
    case result of
        Right val -> return (Just val)
        Left err -> do
            putStrLn $ "Attempt failed with error: " ++ show (err :: SomeException)
            retryIO (n - 1) action

-- Example failing IO action
failingAction :: IO String
failingAction = do
    putStrLn "Trying to read a non-existent file..."
    readFile "non_existent_file.txt"

-- Main function to test retryIO
main :: IO ()
main = do
    putStrLn "Starting retry test:"
    result <- retryIO 3 failingAction
    case result of
        Just content -> putStrLn $ "File read successfully:\n" ++ content
        Nothing      -> putStrLn "Operation failed after retries."
```

---

### 🧪 Example Output (if the file does not exist):

```
Starting retry test:
Trying to read a non-existent file...
Attempt failed with error: main.hs: readFile: does not exist (No such file or directory)
Trying to read a non-existent file...
Attempt failed with error: main.hs: readFile: does not exist (No such file or directory)
Trying to read a non-existent file...
Attempt failed with error: main.hs: readFile: does not exist (No such file or directory)
All attempts failed.
Operation failed after retries.
```

---

### 📌 How It Works:

* `retryIO` wraps the `IO` action using `try`, which catches exceptions.
* If the action fails, it prints the error and retries up to the specified number of attempts.
* After all attempts are exhausted, it returns `Nothing`.
