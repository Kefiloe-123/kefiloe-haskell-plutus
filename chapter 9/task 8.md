HC9T8: Recursive Sequence Data Type

```haskell
-- Define the recursive data type Sequence
data Sequence a = EmptySeq | Node a (Sequence a)
  deriving Show

-- Example sequences
seq1 :: Sequence Int
seq1 = Node 1 (Node 2 (Node 3 EmptySeq))

seq2 :: Sequence String
seq2 = Node "a" (Node "b" (Node "c" EmptySeq))

-- Function to convert Sequence to a Haskell list (for display)
toList :: Sequence a -> [a]
toList EmptySeq     = []
toList (Node x xs)  = x : toList xs

-- Main function to test Sequence
main :: IO ()
main = do
  putStrLn "Sequence of Ints:"
  print (toList seq1)

  putStrLn "\nSequence of Strings:"
  print (toList seq2)
```

---

### ✅ Example Output:

```
Sequence of Ints:
[1,2,3]

Sequence of Strings:
["a","b","c"]
```

---

### ✔️ Explanation:

* `Sequence a` is a **recursive parametric data type**:

  * `EmptySeq`: marks the end of the sequence
  * `Node a (Sequence a)`: holds a value and a reference to the next node
* `toList` is a helper function to convert the custom sequence into a regular list for easy viewing.
