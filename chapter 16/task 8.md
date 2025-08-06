HC16T8: Insertion Sort

```haskell
-- main.hs

-- Define a function to insert an element into the correct position in a sorted list
insert :: Int -> [Int] -> [Int]
insert x [] = [x]                                      -- Insert into empty list
insert x (y:ys)
    | x <= y    = x : y : ys                           -- Place x before y if x is smaller
    | otherwise = y : insert x ys                      -- Keep searching

-- Define the insertion sort function using recursion
insertionSort :: [Int] -> [Int]
insertionSort [] = []                                  -- Empty list is already sorted
insertionSort (x:xs) = insert x (insertionSort xs)     -- Insert head into sorted tail

-- Main function to test insertionSort
main :: IO ()
main = do
    -- Define an unsorted list
    let unsortedList = [5, 2, 9, 1, 7, 3]

    -- Sort the list using insertionSort
    let sortedList = insertionSort unsortedList

    -- Print the results
    putStrLn ("Unsorted list: " ++ show unsortedList)
    putStrLn ("Sorted list: " ++ show sortedList)
```

---

### 🛠️ How to Run:

Save the code to `main.hs` and run it using:

```bash
runghc main.hs
```

Or compile it with:

```bash
ghc main.hs -o insertionSortApp
./insertionSortApp
```

---
