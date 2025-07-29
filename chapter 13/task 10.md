HC13T10: Multi-Module Main Function


```haskell
-- Main.hs
-- This program searches for files containing "txt" in their names,
-- sorts them alphabetically, and prints them.

import System.Directory (listDirectory)
import Data.List (isInfixOf, sort)

main :: IO ()
main = do
  putStrLn "Searching for files containing 'txt' in the current directory..."

  -- Get all files and directories in the current directory
  files <- listDirectory "."

  -- Filter files that contain "txt" in their names
  let filtered = filter (isInfixOf "txt") files

  -- Sort the filtered list
  let sorted = sort filtered

  -- Display the results
  putStrLn "Sorted matching files:"
  mapM_ putStrLn sorted
```

---

### 💡 How to Run

Save the code as `Main.hs`, then compile and run it using:

```bash
ghc Main.hs -o searchFiles
./searchFiles
```

Or run it directly in GHCi:

```bash
ghci Main.hs
*Main> main
```
