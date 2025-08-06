HC15T9: Try Function for File IO Exceptions

```haskell
-- main.hs
-- Demonstrates how to catch file IO exceptions using `try` in Haskell

import System.IO (hFlush, stdout)
import Control.Exception (try, IOException)

-- Function to safely read a file using `try`
readFileSafely :: FilePath -> IO (Either IOException String)
readFileSafely path = try (readFile path)  -- returns Either IOException String

main :: IO ()
main = do
    putStr "Enter the filename to read: "
    hFlush stdout
    fileName <- getLine

    result <- readFileSafely fileName

    case result of
        Left err -> putStrLn $ "An error occurred: " ++ show err
        Right contents -> do
            putStrLn "\n--- File Contents ---"
            putStrLn contents
```

---

### 🧪 Example Runs

**✅ Run with existing file (`hello.txt`)**

```
Enter the filename to read: hello.txt

--- File Contents ---
Hello world!
This is a test file.
```

**❌ Run with missing file**

```
Enter the filename to read: missing.txt
An error occurred: missing.txt: openFile: does not exist (No such file or directory)
```

---

### ✅ Summary

| Feature                | Technique Used          |
| ---------------------- | ----------------------- |
| Catching IO exceptions | `try` function          |
| Friendly error message | `Either` pattern match  |
| Clean file handling    | `readFile` inside `try` |
