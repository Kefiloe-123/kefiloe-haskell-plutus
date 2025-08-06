HC18T3: incrementTreeValues Function

```haskell
-- main.hs

-- Define a binary tree data type
data Tree a
  = Empty
  | Node a (Tree a) (Tree a)
  deriving (Show, Eq)

-- Functor instance for Tree
instance Functor Tree where
  fmap _ Empty = Empty
  fmap f (Node x left right) =
    Node (f x) (fmap f left) (fmap f right)

-- Function to increment all values in the tree using fmap
incrementTreeValues :: Tree Int -> Tree Int
incrementTreeValues = fmap (+1)
-- This leverages the Functor instance: (+1) is applied to every node value

-- Helper function to create a sample tree
sampleTree :: Tree Int
sampleTree =
  Node 10
    (Node 5 Empty Empty)
    (Node 20
      (Node 15 Empty Empty)
      Empty)

-- Main function to demonstrate incrementTreeValues
main :: IO ()
main = do
  putStrLn "Original Tree:"
  print sampleTree

  let incremented = incrementTreeValues sampleTree
  putStrLn "\nTree after incrementing all values:"
  print incremented
```

---

### 💡 What This Does:

* Defines `Tree a` and gives it a `Functor` instance.
* `incrementTreeValues` simply uses `fmap (+1)` to walk the tree and add 1 to each value.
* `main` demonstrates the transformation.

---

### 🛠️ How to Run:

Save this as `main.hs` and run:

```bash
runghc main.hs
```

Or compile it:

```bash
ghc main.hs -o treeIncrement
./treeIncrement
```

---
