HC12T9: Read and Print File Content

```haskell
-- This program reads a filename from the user and prints its contents.
-- It handles the case where the file doesn't exist gracefully.

import System.IO
import Control.Exception (catch, IOException)

-- Function to read and print the contents of a file
printFileContents :: FilePath -> IO ()
printFileContents filename = do
    content <- readFile filename
    putStrLn "File contents:"
    putStrLn content

-- Error handler function
handleReadError :: IOException -> IO ()
handleReadError _ = putStrLn "Error: File not found or could not be read."

-- Main function
main :: IO ()
main = do
    putStrLn "Enter the file name to read:"
    filename <- getLine
    printFileContents filename `catch` handleReadError
```

---

### 🧪 Example:

**Input (file name):**

```
example.txt
```

**Output (if file exists):**

```
File contents:
Hello, this is a test file!
```

**Output (if file doesn't exist):**

```
Error: File not found or could not be read.
```

---

### 🏃 How to run:

* **In terminal (if using GHC locally):**

  ```bash
  ghc Main.hs
  ./Main
  ```

* **In online editors:** This kind of file I/O may not work in sandboxed environments (like mycompiler.io), so test it **locally** for full functionality.

---
