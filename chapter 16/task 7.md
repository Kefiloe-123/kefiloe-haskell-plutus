HC16T7: Element Existence in List

```haskell
-- main.hs

-- Define a function to check if an element exists in a list
elementExists :: (Eq a) => a -> [a] -> Bool
elementExists x xs = x `elem` xs
-- The built-in 'elem' function checks if a value exists in a list
-- The type constraint (Eq a) means the elements must be comparable for equality

-- Main function to test the elementExists function
main :: IO ()
main = do
    -- Define the list
    let myList = [10, 20, 30, 40, 50]
    
    -- Define the element to search for
    let target = 30

    -- Check if the element exists in the list
    if elementExists target myList
        then putStrLn (show target ++ " exists in the list.")
        else putStrLn (show target ++ " does not exist in the list.")
```

---

### 🛠️ How to Run:

Save the file as `main.hs`, then:

```bash
runghc main.hs
```

Or compile it:

```bash
ghc main.hs -o elementCheck
./elementCheck
```

---
