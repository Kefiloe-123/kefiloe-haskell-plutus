HC13T3: Sort and Return Filtered Files

```haskell
-- This program lists all files in the current directory,
-- filters them using a keyword entered by the user,
-- sorts the filtered list alphabetically,
-- and then prints the result.

import System.Directory (listDirectory)
import Data.List (sort, isInfixOf)

-- Function to filter and sort files by a keyword
filterAndSortFiles :: String -> IO [FilePath]
filterAndSortFiles keyword = do
  files <- listDirectory "."                  -- Get all file and folder names in the current directory
  let filtered = filter (isInfixOf keyword) files  -- Filter filenames containing the keyword
  return (sort filtered)                      -- Sort the filtered filenames alphabetically

-- Main function to run the program
main :: IO ()
main = do
  putStrLn "Enter a keyword to filter files:"
  keyword <- getLine                          -- Read keyword from user input
  sortedFiles <- filterAndSortFiles keyword   -- Get the filtered and sorted filenames
  putStrLn "Filtered and sorted files:"
  mapM_ putStrLn sortedFiles                  -- Print each filename on a new line
```

### ✅ How it works:

* `listDirectory "."` lists all items in the current folder.
* `filter (isInfixOf keyword)` keeps only the ones containing the keyword.
* `sort` alphabetically orders the results.
* `main` drives the interaction with the user.

