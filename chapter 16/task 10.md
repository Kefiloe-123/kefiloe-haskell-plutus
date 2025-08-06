HC16T10: Character Frequency in String

```haskell
-- main.hs

import Data.List (group, sort)
import Data.Char (toLower)

-- Function to count frequency of each character in a string
charFrequency :: String -> [(Char, Int)]
charFrequency str = map (\grp -> (head grp, length grp)) groupedChars
  where
    cleaned = map toLower str                 -- Optional: convert all to lowercase for case-insensitive counting
    groupedChars = group $ sort cleaned      -- Sort and group identical characters together

-- Main function to test charFrequency
main :: IO ()
main = do
    let input = "Hello, Haskell!"
    let frequencies = charFrequency input

    putStrLn ("Input string: " ++ input)
    putStrLn "Character frequencies:"
    mapM_ print frequencies
```

---

### 💡 Explanation:

* `sort` arranges characters in order.
* `group` clusters identical characters together.
* Then we map each group to a tuple `(character, count)`.
* Converts all characters to lowercase to count `'H'` and `'h'` as the same character (optional).

---

### 🛠️ How to Run:

Save as `main.hs`, then run with:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o charFreqApp
./charFreqApp
```
