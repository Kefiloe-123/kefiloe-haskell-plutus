HC13T1: List Files in Directory

```haskell
-- This program lists all files and directories in the current directory
-- using the System.Directory module.

import System.Directory (listDirectory)
import System.IO

-- Main function
main :: IO ()
main = do
    putStrLn "Files and directories in the current directory:"
    files <- listDirectory "."  -- Get the list of files in the current directory
    mapM_ putStrLn files         -- Print each file or directory name
```

---

### 🏃 How to Run

1. Save this code as `Main.hs`.
2. In your terminal, navigate to the folder where `Main.hs` is saved.
3. Run the following:

```bash
ghc Main.hs
./Main
```

---

### 🧾 Example Output

```
Files and directories in the current directory:
Main.hs
example.txt
MathOperations.hs
Main
```

---

### 🔎 Notes

* `listDirectory "."` lists **names only**, not full paths.
* It **does not include hidden files** (like `.gitignore`).
* If you want to include full paths or hidden files, we can enhance it using `getDirectoryContents`.
