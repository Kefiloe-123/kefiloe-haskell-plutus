HC1T4 - Task 4: Composing a Function to Process Player Data


---

### ✅ **Complete Haskell Code Example:**

```haskell
import Data.List (sortBy)
import Data.Ord (comparing)

-- Function to extract player names from a list of (name, score) tuples
extractPlayers :: [(String, Int)] -> [String]
extractPlayers players = [name | (name, _) <- players]

-- Function to sort players by score in descending order
sortByScore :: [(String, Int)] -> [(String, Int)]
sortByScore = sortBy (flip (comparing snd))

-- Function to take the top three players
topThree :: [(String, Int)] -> [(String, Int)]
topThree = take 3

-- Composed function to get the top three player names
getTopThreePlayers :: [(String, Int)] -> [String]
getTopThreePlayers = extractPlayers . topThree . sortByScore

-- Main function to demonstrate the functionality
main :: IO ()
main = do
    let players = [("Alice", 45), ("Bob", 72), ("Charlie", 60), ("Daisy", 90), ("Ethan", 55)]
    
    putStrLn "All players and their scores:"
    print players

    putStrLn "\nTop three players:"
    let topPlayers = getTopThreePlayers players
    print topPlayers
```

---

### ▶ **Example Output:**

```
All players and their scores:
[("Alice",45),("Bob",72),("Charlie",60),("Daisy",90),("Ethan",55)]

Top three players:
["Daisy","Bob","Charlie"]
```

---

### 🔍 **Explanation:**

| Function             | What It Does                                                        |
| -------------------- | ------------------------------------------------------------------- |
| `extractPlayers`     | Takes a list like `[("Alice", 45)]` and returns `["Alice"]`.        |
| `sortByScore`        | Sorts the list **by score**, largest to smallest.                   |
| `topThree`           | Takes the first 3 elements of the sorted list.                      |
| `getTopThreePlayers` | Composes the above functions to get the names of the top 3 players. |

---

### ✔ **How to Run:**

1. Save this as `TopPlayers.hs`.
2. Compile with GHC:

   ```bash
   ghc TopPlayers.hs
   ```
3. Run:

   ```bash
   ./TopPlayers
   ```

---
