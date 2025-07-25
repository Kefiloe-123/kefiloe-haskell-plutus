HC12T8: Merge Two Sorted Lists

```haskell
-- This program defines a function mergeLists that merges two sorted lists.
-- It tests the function in the main using example inputs.

-- Function to merge two sorted lists into one sorted list
mergeLists :: Ord a => [a] -> [a] -> [a]
mergeLists [] ys = ys
mergeLists xs [] = xs
mergeLists (x:xs) (y:ys)
    | x < y     = x : mergeLists xs (y:ys)
    | otherwise = y : mergeLists (x:xs) ys

-- Main function to demonstrate usage
main :: IO ()
main = do
    putStrLn "Merging [1,3,5,7] and [2,4,6,8]..."
    let list1 = [1,3,5,7]
    let list2 = [2,4,6,8]
    let merged = mergeLists list1 list2
    putStrLn "Result:"
    print merged
```

---

### 🧾 Example Output:

```
Merging [1,3,5,7] and [2,4,6,8]...
Result:
[1,2,3,4,5,6,7,8]
```

---

### 🛠 How to run:

* Paste into an online Haskell editor like [mycompiler.io](https://www.mycompiler.io/new/haskell), then click **Run**.
* Or save as `Main.hs` and run locally with:

  ```bash
  ghc Main.hs
  ./Main
  ```
