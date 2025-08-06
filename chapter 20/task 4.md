HC20T4: countChars with State Monad

```haskell
-- main.hs

-- Import the required module
import Control.Monad.State
import qualified Data.Map as Map
import Data.Map (Map)

-- Type alias for state that keeps track of character frequencies
type CharCountState = Map Char Int

-- Process each character and update the state map
processChar :: Char -> State CharCountState ()
processChar c = do
    freqMap <- get                      -- Get current state (map)
    let updatedMap = Map.insertWith (+) c 1 freqMap
    put updatedMap                     -- Put updated map back into state

-- Count all characters in a string
countChars :: String -> State CharCountState ()
countChars = mapM_ processChar

-- Main function to run the state and print the result
main :: IO ()
main = do
    let inputStr = "haskell rocks"
        initialState = Map.empty
        finalState = execState (countChars inputStr) initialState

    putStrLn $ "Character frequencies in \"" ++ inputStr ++ "\":"
    mapM_ print (Map.toList finalState)
```

---

### 🔍 Explanation:

* **`processChar`**: Updates the map, adding 1 to the count of the character using `Map.insertWith (+)`.
* **`countChars`**: Applies `processChar` to every character in the input string.
* **`State` Monad**: Tracks the character count as state throughout the computation.

---

### 🛠️ How to run:

1. Save the code in a file named `main.hs`.
2. Run it with:

```bash
runghc main.hs
```

---
