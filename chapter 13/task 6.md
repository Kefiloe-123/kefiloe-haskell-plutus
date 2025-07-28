HC13T6: File Names to Map

```haskell
-- FileMap.hs
-- This program filters file names and stores them in a Map with their lengths.

import System.Directory (listDirectory)
import Data.List (isSuffixOf)
import qualified Data.Map as Map

-- Function to filter file names and map them to their lengths
filesToMap :: [FilePath] -> Map.Map FilePath Int
filesToMap files =
  Map.fromList [(f, length f) | f <- files, ".txt" `isSuffixOf` f]

main :: IO ()
main = do
  putStrLn "Reading files in current directory..."
  allFiles <- listDirectory "."
  let filteredMap = filesToMap allFiles
  putStrLn "Filtered .txt files with their name lengths:"
  print filteredMap
```

---

### 💡 What This Program Does:

* Filters all `*.txt` files
* Creates a key-value map: `filename -> length of filename`
* Prints the map

---

### ✅ How to Run It

1. Save it as `FileMap.hs`
2. In terminal:

   ```bash
   ghc FileMap.hs
   ./FileMap
   ```

---

### 📝 Example Output (if you have `a.txt`, `b.txt`, `hello.hs`):

```
Reading files in current directory...
Filtered .txt files with their name lengths:
fromList [("a.txt",5),("b.txt",5)]
```
