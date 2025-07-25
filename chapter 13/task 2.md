HC13T2: Filter Files by Substring

```haskell
-- This program filters files in the current directory
-- based on a substring in the filename using isInfixOf.

import System.Directory (listDirectory)
import Data.List (isInfixOf)
import System.IO

-- Function to filter filenames containing a given substring
filterFilesBySubstring :: String -> [FilePath] -> [FilePath]
filterFilesBySubstring substring files =
    filter (isInfixOf substring) files

-- Main function
main :: IO ()
main = do
    putStrLn "Enter a substring to search for in filenames:"
    substring <- getLine

    -- Get all files/directories in the current directory
    allFiles <- listDirectory "."

    -- Filter files based on the given substring
    let matchingFiles = filterFilesBySubstring substring allFiles

    -- Print the results
    if null matchingFiles
        then putStrLn "No files found with that substring."
        else do
            putStrLn "Matching files:"
            mapM_ putStrLn matchingFiles
```

---

### 🏃 How to Run

1. Save the code in a file called `Main.hs`.
2. Open your terminal in the same directory.
3. Run:

   ```bash
   ghc Main.hs
   ./Main
   ```

---

### 🧾 Example Usage

**Terminal Input:**

```
Enter a substring to search for in filenames:
hs
```

**Output:**

```
Matching files:
Main.hs
MathOperations.hs
```

---
