HC9T9: Check for Element in a Sequence

```haskell
-- Define the recursive data type Sequence
data Sequence a = EmptySeq | Node a (Sequence a)
  deriving Show

-- Function to check if an element exists in a Sequence
elemSeq :: Eq a => a -> Sequence a -> Bool
elemSeq _ EmptySeq      = False
elemSeq y (Node x xs)
  | x == y    = True
  | otherwise = elemSeq y xs

-- Example sequence
seq1 :: Sequence Int
seq1 = Node 1 (Node 3 (Node 5 (Node 7 EmptySeq)))

-- Main function to test elemSeq
main :: IO ()
main = do
  putStrLn "Check if 3 is in the sequence:"
  print (elemSeq 3 seq1)  -- True

  putStrLn "Check if 4 is in the sequence:"
  print (elemSeq 4 seq1)  -- False
```

---

### ✅ Example Output:

```
Check if 3 is in the sequence:
True
Check if 4 is in the sequence:
False
```

---

### ✔️ Explanation:

* `elemSeq` is a recursive function:

  * Returns `False` if the sequence is empty
  * Checks if the head of the sequence equals the target value
  * If not, it recursively checks the rest of the sequence
* Requires `Eq a =>` so it can compare elements
